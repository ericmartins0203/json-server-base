# json-server-base

Esse é o repositório com a base de JSON-Server + JSON-Server-Auth já configurada, feita para ser usada no desenvolvimento das API's nos Capstones do Q2.

## Endpoints

Assim como a documentação do JSON-Server-Auth traz (https://www.npmjs.com/package/json-server-auth), existem 3 endpoints que podem ser utilizados para cadastro e 2 endpoints que podem ser usados para login.

### Cadastro

POST /register <br/>
POST /signup <br/>
POST /users

Qualquer um desses 3 endpoints irá cadastrar o usuário na lista de "Users", sendo que os campos obrigatórios são os de email e password.
Você pode ficar a vontade para adicionar qualquer outra propriedade no corpo do cadastro dos usuários.

### Login

POST /login <br/>
POST /signin

Qualquer um desses 2 endpoints pode ser usado para realizar login com um dos usuários cadastrados na lista de "Users"

### bedrooms

`GET /bedrooms - FORMATO DA REQUISIÇÃO`

Caso dê tudo certo, a resposta será assim:

```json
[
  {
    "quartoSolteiro": "1"
  },
  {
    "quartoCasal": "4"
  }
]
```

O endpoint da o número de quartos disponíveis, não requer autorização, porém só pode ser alterado por gente autorizada.

### consumption

`GET /consumption - FORMATO DA REQUISIÇÃO`

Caso dê tudo certo, a resposta será assim:

```json
[
  {
    "consumption": "cerveja",
    "quantity": "2",
    "id": 1
  }
]
```

O endpoint da o número de quartos disponíveis, não requer autorização, porém só pode ser alterado por gente autorizada.

`POST /consumption - FORMATO DA REQUISIÇÃO`

```json
{ "consumption": "cerveja", "quantity": "2", "bedroom": "2" }
```

**_ Authorization : bearer token _**
colocar o token do usuário que fez login

Caso dê tudo certo, a resposta será assim:

`POST /consumption - FORMATO DA RESPOSTA - STATUS 201`

```json
{
  "consumption": "cerveja",
  "quantity": "2",
  "bedroom": "2",
  "id": 1
}
```

1. O campo - "consumption": recebe o que foi consumido
2. O campo - "quantity": recebe a quantidade que foi consumida
3. O campo - "bedroom": recebe qual o quarto que consumiu

O endpoint permite criar um consumo, mas a pessoa tem q estar logado.
