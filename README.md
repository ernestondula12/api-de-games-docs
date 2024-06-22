# API de Games
Esta API é utilizada para criação de um game
## Endpoints
### GET /games
Esse endPint é responsavel para retornar todos os games cadastrados na base de dados

#### Parametros
Nenhum
#### Respostas 
##### OK! 200
caso essa resposta acontece voce vai receber a listagem de todos os games.

Exemplo de resposta:
```
[
  {
    "id":1,
    "title":"Call of Duty",
    "year":2019,
    "price":30
  },
  {
    "id":2,
    "title":"Sea of thieves",
    "year":2018,
    "price":40
  },
  {
    "id":3,
    "title":"Minecraft",
    "year":2012,
    "price":20
  }
]
```
##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição.
Motivos: Token inválido, Token exprirado

Exemplo de resposta:
```
{
    "err": "Token inválido"
}
```

## Endpoints
### POST /auth
Esse endPint é responsavel por fazer o processo de login

#### Parametros
Email: E-mail do usuario cadastrado no sistema
password: password do usuario cadastrado no sistema

Exemplo:
```
{
    "email": "ernestondulandula@gmail.com",
    "password": "Millerinho"
}
```
#### Respostas 
##### OK! 200
caso essa resposta acontece voce vai receber o token JWT para conseguir acessar endpoints protegidos na API. 

Exemplo de resposta:
```
{
"token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiZW1haWwiOiJlcm5lc3RvbmR1bGFuZHVsYUBnbWFpbC5jb20iLCJpYXQiOjE3MTkwNDYwNzQsImV4cCI6MTcxOTIxODg3NH0.s4Yv3EFe3Chmg6LzLcQNYBdIL_I2IwykfkqwDN80bQU"
}
```

##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição.
Motivos: Token inválido, Token exprirado

Exemplo de resposta:
```
{err: "Credenciais inválidas!"}
```
