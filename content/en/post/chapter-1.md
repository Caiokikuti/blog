---
date: 2021-04-08T10:58:08-04:00
description: "Simple CRUD required to development jobs"
featured_image: "/images/feather-react.png"
tags: ["API", "REST", "JS", "TS"]
title: "Potential Crud"
---
# API POTENTIAL CRUD REST - Feathers js

## Descrição

<p>Projeto de uma API REST utilizando o framework Feathers e o DB PostgreSQL</p>

## Tópicos

<!--ts-->

- [Descrição](#descrição)
- [Features](#features)
- [Pré-requisitos](#pré-requisitos)
- [Executar](#executar)
- [Endpoints](#endpoints)
- [Front-end](#front-end)
- [Tecnologias utilizadas](#tecnologias)
- [Testes](#testes)
- [Repository](#repository)
- [Autor](#autor)
<!--te-->

## Features

- [x] Autenticação de usuário usando jwt
- [x] Listagem de todos os desenvolvedores
- [x] Listagem de desenvolvedor por ID
- [x] Listagem de desenvolvedor pelos atributos nome, sexo, idade, data de nascimento e hobby
- [x] Busca de de desenvolvedor pelos atributos nome, sexo, idade, data de nascimento e hobby
- [x] Cadastro de desenvolvedor
- [x] Exclusão de desenvolvedor
- [x] Edição de dado do desenvolvedor

## Pré-requisitos

<p>Para rodar o projeto são necessárias as técnologias Nodejs e Docker</p>

## Executar

<p>Para subir o banco e a API basta rodar o comando:</p>

```bash
docker-compose up -d
```

<p>Para rodar os scripts de migração de tabela é necessário rodar:</p>

```bash
npm install -g db-migrate
```

<p>Em sequencia execute a migração pelo comando:</p>

```bash
db-migrate up
```

<p>Após subir os containers e realizar as migrações a api ficará alocada na porta 3030 (acesso por: http://localhost:3030 ) e o banco ficara alocado na porta 5432 </p>

<p>Caso deseje parar a execução do container, utilize:</p>

```bash
docker-compose down
```

## Endpoints

<p>Para cadastrar um user utilize o endpoint http://localhost:3030/users, por exemplo:<p>

```json
{
  "email": "admin@admin.com",
  "password": "admin"
}
```

<p>O cadastro de um usuário é necessário para que seja feita a autenticação via jwt.
Para recuperar esse token jwt e utilizá-lo nas requisições é necessário acessar o endpoint http://localhost:3030/authentication passando as credências do usuário e a estratégia<p>

```json
{
  "email": "admin@admin.com",
  "password": "admin",
  "strategy": "local"
}
```

<p> POST: Para realizar um POST de desenvolvedor é necessário passar no header Authorization da requisição o Bearer Token. Para chamar o post basta acessar:  http://localhost:3030/developers e passar um corpo no formato abaixo:<p>  
  
 ```json
{
	"nome": "Vini",
	"idade": 15,
	"hobby": "Programar",
  "sexo": "M",
	"dataNascimento": "1943-01-17"
}
``` 
<p> GET: Para realizar um GET de desenvolvedor é necessário passar no header Authorization da requisição o Bearer Token. Para chamar o GET basta acessar:  http://localhost:3030/developers. Alguns parametros para busca podem ser passados conforme mostrado abaixo:<p>

- http://localhost:3030/developers/1 (Retorna usuario com o id igual a 1)
- http://localhost:3030/developers?nome[$like]=Vini (Busca usuarios com nome contendo Vini)
- http://localhost:3030/developers?hobby[$like]=programar (Busca usuarios com dado hobby)
- http://localhost:3030/developers?sexo[$like]=M (Busca usuarios com dado sexo)
- http://localhost:3030/developers?dataNascimento=1943-01-17 (Busca usuarios com dada data de nascimento)
- Vale ressaltar que os parâmetros das buscas são combináveis.

<p> PUT: Para realizar um PUT em um desenvolvedor é necessário passar no header Authorization da requisição o Bearer Token. Para chamar o PUT basta acessar:  http://localhost:3030/developers/{id do desenvolvedor}. Você pode modificar alguma informação do json abaixo<p>

```json
{
  "nome": "Vini",
  "idade": 15,
  "hobby": "Programar",
  "sexo": "M",
  "dataNascimento": "1943-01-17"
}
```

<p> DELETE: Para realizar um DELETE em um desenvolvedor é necessário passar no header Authorization da requisição o Bearer Token. Para chamar o DELETE basta acessar:  http://localhost:3030/developers/{id do desenvolvedor}.<p>

## Front-end

<p> Todos os endpoints acima podem ser chamados pelo POSTMAN ou Insominia. Caso deseje, também foi desenvolvido um Front-end simples com intuito de facilitar o teste<p>

- [Front-end](https://github.com/Caiokikuti/Potential-crud-UI)

## Tecnologias

<p>As seguintes ferramentas foram utilizadas na construção do projeto:</p>

- [Node.js](https://nodejs.org/en/)
- [Feathers](https://docs.feathersjs.com/)
- [PostgresSQL](https://www.postgresql.org/)
- [DB-Migrate](https://www.npmjs.com/package/db-migrate)
- [Docker](https://www.docker.com/products/docker-desktop)
- [Mocha](https://mochajs.org/)

## Testes

<p>Para a realização dos testes unitários, execute:</p>

```bash
yarn test
```

## Repository 
- [Link to github](https://github.com/Caiokikuti/Potential-Crud)

## Autor

---

<a href="https://www.linkedin.com/in/caio-eduardo-kikuti-machado">
 <img style="border-radius: 50%;" src="https://avatars.githubusercontent.com/u/37967111?v=4" width="100px;" alt=""/>
 <br />
 <sub><b>Caio Eduardo Kikuti Machado</b></sub></a> <a href="https://www.linkedin.com/in/caio-eduardo-kikuti-machado"> </a>

Contatos:

[![Linkedin Badge](https://img.shields.io/badge/-Caio-blue?style=flat-square&logo=Linkedin&logoColor=white&link=https://www.linkedin.com/in/caio-eduardo-kikuti-machado)](https://www.linkedin.com/in/caio-eduardo-kikuti-machado)
[![Gmail Badge](https://img.shields.io/badge/-jakcaio@gmail.com-c14438?style=flat-square&logo=Gmail&logoColor=white&link=mailto:jakcaio@gmail.com)](mailto:jakcaio@gmail.com)

