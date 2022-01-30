# 📝 API REST Todo App

🗯️ API Rest de **todos**, sendo possível criar, atualizar, listar e deletar **todos**. Essa API foi construída para estudos e prática de conhecimentos em Node.js e Express.js. Essa API é um desafio proposto da plataforma de ensino Rocketseat.

# Criar usuário - POST /users

- Request (application/json)

  - Body

    | Parâmetro  | Tipo     | Descrição                                                     |
    | ---------- | -------- | ------------------------------------------------------------- |
    | `name`     | `String` | Nome completo da pessoa.                                      |
    | `username` | `String` | Nome de usuário que será utilizado para realizar requisições. |

- Response - 200 (application/json)

  - Body

    ```json
    {
      "id": "a7cb0cec-e56c-4b3e-bf80-eec7e8f1a908",
      "name": "Eric Hahn",
      "username": "erich4hn",
      "todos": []
    }
    ```

# Listar todos - GET /todos

- Request

  - Header

    | Parâmetro  | Tipo     | Descrição                                        |
    | ---------- | -------- | ------------------------------------------------ |
    | `username` | `String` | Nome de usuário usado para realizar requisições. |

- Response - 200 (application/json)

  - Body

    ```json
    [
      {
        "id": "b345cfc3-c5fe-43cd-9a81-45bfa25bd2e4",
        "title": "Eric Hahn",
        "done": false,
        "deadline": "2022-01-29T00:00:00.000Z",
        "created_at": "2022-01-30T17:13:57.789Z"
      }
    ]
    ```

# Criar todo - POST /todos

- Request

  - Body

    | Parâmetro  | Tipo     | Descrição                                                                       |
    | ---------- | -------- | ------------------------------------------------------------------------------- |
    | `title`    | `String` | Título do todo.                                                                 |
    | `deadline` | `String` | Data de prazo final do todo. Recomendado colocar o formato da data: ANO-MES-DIA |

  - Header

    | Parâmetro  | Tipo     | Descrição                                        |
    | ---------- | -------- | ------------------------------------------------ |
    | `username` | `String` | Nome de usuário usado para realizar requisições. |

- Response - 201 (application/json)

  - Body

    ```json
    {
      "id": "7f543dd7-f762-48dd-b01c-de2aa149c96a",
      "title": "Eric Hahn",
      "done": false,
      "deadline": "2022-01-29T00:00:00.000Z",
      "created_at": "2022-01-30T17:20:53.527Z"
    }
    ```

# Atualizar todo - PUT /todos/:id

- Request

  - Route

    | Parâmetro | Tipo     | Descrição                       |
    | --------- | -------- | ------------------------------- |
    | `id`      | `String` | id do todo que será atualizado. |

  - Body

    | Parâmetro  | Tipo     | Descrição                                                                       |
    | ---------- | -------- | ------------------------------------------------------------------------------- |
    | `title`    | `String` | Título do todo.                                                                 |
    | `deadline` | `String` | Data de prazo final do todo. Recomendado colocar o formato da data: ANO-MES-DIA |

  - Header

    | Parâmetro  | Tipo     | Descrição                                        |
    | ---------- | -------- | ------------------------------------------------ |
    | `username` | `String` | Nome de usuário usado para realizar requisições. |

- Response - 200 (application/json)

  - Body

    ```json
    {
      "id": "7f543dd7-f762-48dd-b01c-de2aa149c96a",
      "title": "Teste Update",
      "done": false,
      "deadline": "2022-01-29T00:00:00.000Z",
      "created_at": "2022-01-30T17:20:53.527Z"
    }
    ```

# Concluir todo - PATCH /todos/:id/done

- Request

  - Route

    | Parâmetro | Tipo     | Descrição                       |
    | --------- | -------- | ------------------------------- |
    | `id`      | `String` | id do todo que será atualizado. |

  - Header

    | Parâmetro  | Tipo     | Descrição                                        |
    | ---------- | -------- | ------------------------------------------------ |
    | `username` | `String` | Nome de usuário usado para realizar requisições. |

- Response - 200 (application/json)

  - Body

    ```json
    {
      "id": "7f543dd7-f762-48dd-b01c-de2aa149c96a",
      "title": "Todo concluido e propriedade done marcada como true",
      "done": true,
      "deadline": "2022-01-29T00:00:00.000Z",
      "created_at": "2022-01-30T17:20:53.527Z"
    }
    ```

# Deletar todo - DELETE /todos/:id

- Request

  - Route

    | Parâmetro | Tipo     | Descrição                     |
    | --------- | -------- | ----------------------------- |
    | `id`      | `String` | id do todo que será deletado. |

  - Header

    | Parâmetro  | Tipo     | Descrição                                        |
    | ---------- | -------- | ------------------------------------------------ |
    | `username` | `String` | Nome de usuário usado para realizar requisições. |

- Response - 204 (application/json)

  - Body

# Pré-requisitos

- `Node.js`

# Instalação

Para instalar as dependências do projeto é necessário ter o yarn instalado, o yarn está contido no Corepack do Node.js.

Node.js >= 16.10, execute:

> `corepack enable`

Node.js < 16.10, execute:

> `npm i -g corepack`

Após ter instalado o Yarn, execute o comando a seguir na pasta do repositório clonado:

> `yarn install`

Após ter instalado as dependências, execute o comando para iniciar o servidor em desenvolvimento:

> ```
> yarn dev
> # O servidor executará em: http://localhost:3333 #
> ```

# Executando testes

Para executar os testes automatizados, usamos o comando:

> `yarn test`

# Tecnologias usadas

- [Node.js](https://nodejs.org/pt-br/)
- [Express](https://expressjs.com/pt-br/)
- [Nodemon](https://github.com/remy/nodemon)
- [Jest](https://jestjs.io/pt-BR/)

# Autor

|👔 Eric Hahn|
|--
|![](https://avatars.githubusercontent.com/u/22550836?v=4&s=180)|
