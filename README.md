# api-de-games-docs
Esta API e utilizada para.......

## Endpoints
### GET /games
Essse endpoint é responsável por retornar a listagem de todos os games cadastrados no banco de dados. 
#### Parametros
Nenhum
#### Repostas
##### OK 200
Caso essa resposta aconteça você vai receber a listagem de todos os games.
Exemplo de resposta: 

```
[
    {
        "id": 23,
        "title": "Call of duty MW",
        "year": 2019,
        "price": 60
    },
    {
        "id": 65,
        "title": "Sea of thieves",
        "year": 2018,
        "price": 40
    },
    {
        "id": 2,
        "title": "Minecraft",
        "year": 2012,
        "price": 20
    }
]
```

##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos: Token inválido,
Token expirado.
Exemplo de resposta:
```
{
    "err": "Token inválido!"
}
```

### POST /auth
Essse endpoint é responsável por fazer login. 
#### Parametros
email: E-mail do usuário cadastrado no sistema. 
password: Senha do usuário cadastrado no sistema, com aquele determinado e-mail.

Exemplo:
```
{
      email: "victordevtb@guiadoprogramador.com",
      password: "nodejs<3"
}
```

#### Repostas
##### OK 200
Caso essa resposta aconteça você vai receber o token JWT para conseguir acessar endpoints protegidos na API.

Exemplo de resposta: 

```
{
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MjAsImVtYWlsIjoiZ3VpZ2dAZ21haWwuY29tIiwiaWF0IjoxNjM5MDU4NTgzLCJleHAiOjE2MzkyMzEzODN9.24zzoHuSWU4WXR26PnQJbJHJtpBdKjBEcWX4siLzljE"
}
```

##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos: Senha ou Email incorreto.

Exemplo de resposta:
```
{
    "err": "Credenciais inválidas!!"
}
```

