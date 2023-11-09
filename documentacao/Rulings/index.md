## Rulings -> Index

### 1. Listagem de todas as pautas

### Requisição para API

#### 1. Rota da API

GET-> `api/rulings`

#### 2. Parâmetros e Suas Utilidades

Sem parâmetros

#### 3. Exemplo de Requisição

GET -> `api/rulings`

Body:

```json
{}
```

### Retorno da API

#### Sucesso

Retorna um json contendo uma lista com as pautas da empresa atual e suas informações.

**Ex**:

```json
{
  "Rulings": [
    {
      "id": 1,
      "company_id": 1,
      "name": "Exemplo 1",
      "active": null,
      "deleted": null,
      "created": "2023-11-09T12:20:15-03:00",
      "modified": "2023-11-09T12:23:19-03:00",
      "created_by": 3,
      "deleted_by": null
    },
    {
      "id": 2,
      "company_id": 1,
      "name": "Exemplo 1",
      "active": null,
      "deleted": null,
      "created": "2023-11-09T12:20:15-03:00",
      "modified": "2023-11-09T12:23:19-03:00",
      "created_by": 3,
      "deleted_by": null
    }
  ],
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando ver as pautas da empresa que participa

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Você não tem permissão para acessar este recurso."
    }
    ```

### 2. Listagem com o nome e id

### Requisição para API

#### 1. Rota da API

GET -> `api/rulings?list_all=basic`

#### 2. Parâmetros e Suas Utilidades

list_all: recebe a palavra `basic` para indicar que a listagem é de apenas o id e o nome das pautas

#### 3. Exemplo de Requisição

GET -> `api/rulings?list_all=basic`

Body:

```json
{}
```

### Retorno da API

#### Sucesso

Retorna um json contendo uma lista com o id e o nome de cada uma das pautas da empresa atual.
**Ex**:

```json
{
  "Rulings": {
    "1": "Exemplo 1",
    "2": "Exemplo 2"
  },
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando ver as pautas da empresa que participa

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Você não tem permissão para acessar este recurso."
    }
    ```
