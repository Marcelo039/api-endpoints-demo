# API de Livros

API REST feita com Node.js e Express para gerenciar livros. Os dados são armazenados localmente em `livros.json`.

## Instalação e execução

```bash
npm install
node app.js
```

A API estará disponível em `http://localhost:8000`.

Para desenvolvimento, use `npx nodemon app.js`.

## Endpoints

| Método   | Rota          | Ação              |
| -------- | ------------- | ----------------- |
| `GET`    | `/livros`     | Lista os livros   |
| `GET`    | `/livros/:id` | Busca um livro    |
| `POST`   | `/livros`     | Cadastra um livro |
| `PATCH`  | `/livros/:id` | Atualiza um livro |
| `DELETE` | `/livros/:id` | Remove um livro   |

Exemplo de cadastro:

```bash
curl -X POST http://localhost:8000/livros \
  -H "Content-Type: application/json" \
  -d "{\"id\":\"7\",\"nome\":\"O Hobbit\"}"
```

O campo `nome` é obrigatório. As respostas usam JSON nas consultas e mensagens de texto nas operações de cadastro, atualização e remoção.

## Estrutura

```text
app.js                  # Inicialização do servidor
livros.json             # Armazenamento local
controladores/livro.js  # Controladores HTTP
rotas/livro.js          # Rotas da API
servicos/livro.js       # Operações sobre os dados
```

Projeto licenciado sob ISC.
