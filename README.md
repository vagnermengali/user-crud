##

<h1 align="center">
  User Crud
</h1>

<p align = "center">
Este é um crud de usuário que visa facilitar o acesso com funcionalidades básicas de um usuário e login.
</p>

<p align="center">
  <a href="#instalação">Instalação</a>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <a href="#endpoints">Endpoints</a>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <a href="#swagger">Swagger</a>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</p>

## **Instalação**

A seguir esta o passo-a-passo de instalação e execução em ambiente de desenvolvimento<br/>

A url base da api é http://localhost:3000

<p>1. Clone o repositório:</p>

```
git clone https://github.com/vagnermengali/user-crud
```

<p>2. Adentre na pasta raiz do projeto:</p>
  
```
cd user-crud
```
<p>3. Instale as dependências do projeto:</p>

```
yarn ou yarn install
```

<p>4. Crie seu schema:</p>

```
yarn prisma generate
```

<p>7. Aplique suas migrações:</p>
  
```
yarn prisma migrate dev
```
<p>8. Ative o server:</p>

```
yarn start:dev
```

<p align ='center'><a href="#--user-crud" >Voltar ao início</a></p>

---

## **Endpoints**

A API esta divida em /users sendo um CRUD e /login para geraão do token e melhor interação com a api. <br/>

<h2 align ='center'> Usuário </h2>

Nessa rotas o usuário pode acessar sem o token apenas POST/users, as demais usará o token para executar o CRUD de usuário :

##

`GET /users - FORMATO DA REQUISIÇÃO`

```
Não é necessário um corpo da requisição.

```

`GET /users - FORMATO DA RESPOSTA - STATUS 200`

```json
[
  {
    "username": "UserCrud UserCrud",
    "email": "user@gmail.com",
    "created_at": "2023-02-13T14:30:59.868Z",
    "updated_at": "2023-02-13T14:30:59.868Z"
  },
  {
    "username": "CrudUser CrudUser",
    "email": "crud@gmail.com",
    "created_at": "2023-02-13T13:08:00.947Z",
    "updated_at": "2023-02-13T14:33:49.762Z"
  }
]
```

##

`GET /users/profile - FORMATO DA REQUISIÇÃO`

```
Não é necessário um corpo da requisição.
```

`GET /users/profile - FORMATO DA RESPOSTA - STATUS 201`

```json
{
  "id": "fb6f2944-3ddc-4cef-a217-c0de75a1ee04",
  "username": "CrudUser CrudUser",
  "email": "crud@gmail.com",
  "created_at": "2023-02-13T13:08:00.947Z",
  "updated_at": "2023-02-13T14:31:49.390Z"
}
```

##

`POST /users - FORMATO DA REQUISIÇÃO`

```json
{
  "first_name": "UserCrud",
  "last_name": "UserCrud",
  "email": "user@gmail.com",
  "password": ".Crud123"
}
```

`POST /users- FORMATO DA RESPOSTA - STATUS 201`

```json
{
  "id": "6556e127-0518-4407-bd3e-65f5cdf1e869",
  "username": "UserCrud UserCrud",
  "email": "user@gmail.com",
  "password": "$2a$10$IrAEhGwMky/3ntH.aJA3ZuKgJnbpziUzcXTqlqyV33NGWJQH/EhEe",
  "created_at": "2023-02-13T14:30:59.868Z"
}
```

##

`PATCH /users/update - FORMATO DA REQUISIÇÃO`

Todos os campos são opcionais

```json
{
  "first_name": "CrudUser",
  "last_name": "CrudUser",
  "email": "crud@gmail.com",
  "password": ".User123"
}
```

`PATCH /users/update/ - FORMATO DA RESPOSTA - STATUS 200`

```json
{
  "id": "fb6f2944-3ddc-4cef-a217-c0de75a1ee04",
  "username": "CrudUser CrudUser",
  "email": "crud@gmail.com",
  "created_at": "2023-02-13T13:08:00.947Z",
  "updated_at": "2023-02-13T14:31:49.390Z"
}
```

##

`DELETE /users/delete/ - FORMATO DA REQUISIÇÃO`

```
Não é necessário um corpo da requisição.
```

`DELETE /users/delete/ - FORMATO DA RESPOSTA - STATUS 204`

```
Não a corpo de retorno.
```

##

<h2 align ='center'> Login </h2>

Nessa rota o usuário pode acessar sem o token para efetuar o login :

##

`POST /login - FORMATO DA REQUISIÇÃO`

```json
{
  "email": "user@gmail.com",
  "password": ".Crud123"
}
```

`POST /login - FORMATO DA RESPOSTA - STATUS 201`

```json
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6InVzZXJAZ21haWwuY29tIiwiaWF0IjoxNjc2Mjk4NjQ2LCJleHAiOjE2NzYzODUwNDYsInN1YiI6IjdmY2M3MzY4LWZhZWEtNGIzZi1hYjhiLWRlODZjNTQ3ZTA5NyJ9.5IVEZ9popPzx3a7T0vPDI2ZlnnNISxBtPJREd7Zi2HE"
}
```

<p align ='center'><a href="#--user-crud" >Voltar ao início</a></p>

---

## **Swagger**

Api também conta a rota de interação, manipulação e documentação mais detalhada.

`api/`

<p align ='center'><a href="#--user-crud" >Voltar ao início</a></p>

---

<p align ='center'> Copyright <a href="https://github.com/vagnermengali">Vagner Mengali</a> 2023 </p>
