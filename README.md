### Cadastro

POST /register <br/>
POST /signup <br/>
POST /users

exemplo de entrada

```json
{ "email": "kenzinho@mail.com", "password": "123456" }
```

exemplo de saida

```json
{
  "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImtlbnppbmhvMkBtYWlsLmNvbSIsImlhdCI6MTYzNTUzMjkxMiwiZXhwIjoxNjM1NTM2NTEyLCJzdWIiOiIyIn0.xs9NxcaoeV55yaX6W6iVbQR4eYDAH8wfM9XAmChDa3E",
  "user": {
    "email": "kenzinho2@mail.com",
    "id": 2
  }
}
```

Qualquer um desses 3 endpoints irá cadastrar o usuário na lista de "Users", sendo que os campos obrigatórios são os de email e password.
Você pode ficar a vontade para adicionar qualquer outra propriedade no corpo do cadastro dos usuários.

### Login

POST /login <br/>

exemplo de entrada

```json
{ "email": "kenzinho@mail.com", "password": "123456" }
```

exemplo de saida

```json
{
  "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImtlbnppbmhvQG1haWwuY29tIiwiaWF0IjoxNjM1NTMyNDgxLCJleHAiOjE2MzU1MzYwODEsInN1YiI6IjEifQ.5n59wwmR6H5XsXrIN4fX699aGyN0qKEavSzGwUX-mac",
  "user": {
    "email": "kenzinho@mail.com",
    "name": "Kenzinho",
    "age": 38,
    "id": 1
  }
}
```

Qualquer um desses 2 endpoints pode ser usado para realizar login com um dos usuários cadastrados na lista de "Users"

### Task

GET /tasks

O método não precisa de nenhuma entrada, mas precisa de autorização.

_ Authorization : bearer token _ colocar o token do usuário que fez login

POST /tasks

O método requer entrada e autorização.

_ Authorization : bearer token _ colocar o token do usuário que fez login

exemplo de entrada

```json
{
  "title": "study",
  "completed": false,
  "userId": 5,
  "description": "study typescript"
}
```

exemplo de saida

```json
{
  "id": 5,
  "title": "study",
  "completed": false,
  "userId": 5,
  "description": "study typescript"
}
```

PATCH /tasks/id

O método requer o id do item a ser modificado, entada e autorização.

_ Authorization : bearer token _ colocar o token do usuário que fez login


```json
{
  "completed": true,
}
```

exemplo de saida

```json
{
  "id": 5,
  "title": "study",
  "completed": true,
  "userId": 5,
  "description": "study typescript"
}
```

DELETE /tasks/id

O método requer o id do item a ser excluido e autorização.

_ Authorization : bearer token _ colocar o token do usuário que fez login

