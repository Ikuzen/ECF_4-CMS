PARTIE BACK:
note : changer le DATABASE_USERNAME et DATABASE_PASSWORD dans database.js


requête 1 : authentifier en tant que user
POST / localhost:1337/auth/local
Body : 
{
    "identifier":"yannis.samba@gmail.com",
    "password": "password"
}

requête 2.1 : creation d'un subject en tant que user

POST / localhost:1337/subjects
Body: {
    "title":"my subject",
    "creator_id":1,
}
Header: {le token}

requête 2.2 : creation d'un message lié à un subject en tant que user

POST / localhost:1337/messages
Body: {
    "body":"blablabla",
    "author_id":1,
    "subject_id":1
}
Header: {le token}

requête 4.1 : consulter un sujet de discussion
GET / localhost:1337/subjects/1
Header: {le token}

requête 4.2 : consulter un message associé à un sujet de discussion
GET / localhost:1337/messages?author_id=1
Header: {le token}

requête 4.3 : consulter un message et son auteur

GET / localhost:1337/messages/1
Header: {le token}


Partie front :
https://aa323275811.wordpress.com/