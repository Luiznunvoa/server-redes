# API de Chat em Tempo Real

Este projeto é uma API backend robusta para uma aplicação de chat em tempo real, desenvolvida para a disciplina de Redes de Computadores da Universidade Federal Fluminense. Ele fornece um conjunto completo de funcionalidades para gerenciamento de usuários, conversas e mensagens.

## Funcionalidades

- **Gerenciamento de Usuários**: Registre e autentique usuários de forma segura utilizando JWT.
- **Conversas**: Crie novos canais de conversa.
- **Participantes**: Adicione usuários a conversas existentes.
- **Mensagens**: Envie e receba mensagens dentro de uma conversa.
- **Perfil de Usuário**: Obtenha o perfil do usuário autenticado.
- **Persistência de Dados**: Por meio de um banco de dados Postgres, os dados de conversas são persistentes.

## Tecnologias Utilizadas

O projeto foi construído com uma stack moderna e performática:

- **[Node.js](https://nodejs.org/)**: Ambiente de execução JavaScript.
- **[Fastify](https://www.fastify.io/)**: Framework web para Node.js, focado em performance e baixo overhead.
- **[TypeScript](https://www.typescriptlang.org/)**: Superset de JavaScript que adiciona tipagem estática.
- **[Prisma](https://www.prisma.io/)**: ORM de última geração para Node.js e TypeScript.
- **[PostgreSQL](https://www.postgresql.org/)**: Sistema de banco de dados relacional de código aberto.
- **[Docker](https://www.docker.com/)**: Plataforma para desenvolvimento, deploy e execução de aplicações em contêineres.

## Como executar localmente

Para executar o projeto localmente, siga os seguintes passos:

1. **Clone o repositório:**

   ```bash
   git clone https://github.com/Luiznunvoa/server-redes
   ```

2. **Instale as dependências:**

   ```bash
   npm install
   ```

3. **Inicie o banco de dados com Docker:**

   ```bash
   docker-compose up -d
   ```

4. **Execute as migrações do banco de dados:**

   ```bash
   npx prisma migrate dev
   ```

5. **Inicie o servidor de desenvolvimento:**

   ```bash
   npm run start:dev
   ```

O servidor estará disponível em `http://localhost:3000`.

## Rotas da API

A seguir estão listadas as rotas da API e suas funcionalidades:

### Autenticação

- **`POST /users`**: Registra um novo usuário.
- **`POST /sessions`**: Autentica um usuário e retorna um token de acesso.
- **`GET /profile`**: Retorna o perfil do usuário autenticado.

### Conversas

- **`POST /conversations`**: Cria uma nova conversa.
- **`GET /conversations`**: Retorna as conversas do usuário autenticado.
- **`POST /conversations/add-user/:conversationId`**: Adiciona um usuário a uma conversa.
- **`GET /conversations/users/:conversationId`**: Retorna os usuários de uma conversa.

### Mensagens

- **`POST /conversations/messages/:conversationId`**: Envia uma mensagem em uma conversa.
- **`GET /conversations/messages/:conversationId`**: Retorna as mensagens de uma conversa.
