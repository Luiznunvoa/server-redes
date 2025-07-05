# My Back End

Este é o projeto de back-end para a matéria de Redes de Computadores.

## Como executar localmente

Para executar o projeto localmente, siga os seguintes passos:

1. **Clone o repositório:**

```bash
git clone https://github.com/seu-usuario/seu-repositorio.git
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
