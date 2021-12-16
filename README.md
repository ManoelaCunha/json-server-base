# json-server-base

Esse é o repositório com a base de JSON-Server + JSON-Server-Auth já configurado, usado no desenvolvimento da API da Atividade - JSON-Server do início ao Deploy.

## Endpoints

A API tem um total de 4 endpoints, sendo em volta principalmente do usuário que pode cadastrar as linguas que conhece e as experiências de trabalho.

O url base da API é https://activity-kenzie-json-server.herokuapp.com

### Cadastro

**POST /users - FORMATO DA REQUISIÇÃO**

```javascript
{
"email": "kenzinha@mail.com",
"password": "123456",
"name": "Kenzinha",
"age": 20
}
```

**POST /users - FORMATO DA RESPOSTA - STATUS 201**

```javascript
"user": {
"email": "kenzinha@mail.com",
"name": "Kenzinha",
"age": 20,
"id": 3
}
```

### Login

**POST /login - FORMATO DA REQUISIÇÃO**

```javascript
{
"email": "kenzinho@mail.com",
"password": "123456"
}
```

**POST /login - FORMATO DA RESPOSTA - STATUS 200**

```javascript
"user": {
"email": "kenzinho@mail.com",
"name": "Kenzinho",
"age": 38,
"id": 1
}
```

### Languages

**POST /languages - FORMATO DA REQUISIÇÃO**

```javascript
{
"language": "portuguese",
"level": "fluent",
"userId" : 1
}
```

**POST /languages - FORMATO DA RESPOSTA - STATUS 201**

```javascript
{
"language": "portuguese",
"level": "fluent",
"userId": 1,
"id": 3
}
```

**Listando Languages** - _Não Precisa de Autenticação_

**GET /languages - FORMATO DA RESPOSTA - STATUS 200**

```javascript
[
  {
    language: "english",
    level: "intermediate",
    userId: 1,
    id: 1,
  },
  {
    language: "german",
    level: "basic",
    userId: 1,
    id: 2,
  },
  {
    language: "portuguese",
    level: "fluent",
    userId: 1,
    id: 3,
  },
];
```

### Experience

**POST /experience - FORMATO DA REQUISIÇÃO**

```javascript
{
"company": "Innovation",
"occupation": "Full stack developer",
"userId" : 1
}
```

**POST /experience - FORMATO DA RESPOSTA - STATUS 201**

```javascript
{
"company": "Innovation",
"occupation": "Full stack developer",
"userId": 1,
"id": 2
}
```

**Listando Experiences** - _Precisa de Autenticação_

**GET /experience - FORMATO DA RESPOSTA - STATUS 200**

```javascript
[
  {
    company: "Tech",
    occupation: "Back-end developer",
    userId: 1,
    id: 1,
  },
  {
    company: "Innovation",
    occupation: "Full stack developer",
    userId: 1,
    id: 2,
  },
];
```
