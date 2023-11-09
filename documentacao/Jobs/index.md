## Index

### Requisição para API

### 1. Listagem de todas as funções

#### Rota da API

GET -> `api/jobs`

#### Parâmetros e Suas Utilidades

Sem parâmetros

#### Exemplo de Requisição

GET -> `api/jobs`

Body:

```json
{}
```

### Retorno da API

#### Sucesso

Retorna um json contendo uma lista com as funções da empresa atual e suas informações.

**Ex**:

    ```json
    {
    "Jobs": [
        {
        "id": 1,
        "name": "Exemplo 1",
        "company_id": 1,
        "created": "2023-08-29T15:46:53-03:00",
        "modified": "2023-08-29T16:54:40-03:00",
        "active": true,
        "deleted": null,
        "created_by": 3,
        "deleted_by": null
        },
        {
        "id": 2,
        "name": "Exemplo 2",
        "company_id": 1,
        "created": "2023-08-29T16:54:33-03:00",
        "modified": "2023-08-29T16:54:33-03:00",
        "active": true,
        "deleted": null,
        "created_by": 3,
        "deleted_by": null
        }
    ],
    "status": 1
    }
    ```

#### Erro(s)

1.  Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando ver as funções da empresa que participa

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Você não tem permissão para acessar este recurso."
    }
    ```

### 2. Listagem com o nome e id

#### Rota da API

GET -> `api/jobs?list_all=basic`

#### Parâmetros e Suas Utilidades

list_all: recebe a palavra `basic` para indicar que a listagem é de apenas o id e o nome das funções

#### Exemplo de Requisição

GET -> `api/jobs?list_all=basic`

Body:

```json
{}
```

### Retorno da API

#### Sucesso

Retorna um json contendo uma lista com o id e o nome de cada uma das funções da empresa atual.
**Ex**:

```json
{
  "Jobs": {
    "1": "Exemplo 1",
    "2": "Exemplo 2"
  },
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando ver as funções da empresa que participa

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Você não tem permissão para acessar este recurso."
    }
    ```
