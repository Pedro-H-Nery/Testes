## Units -> Index

### 1. Listagem de todas as unidades

### Requisição para API

#### 1. Rota da API

GET-> `api/units`

#### 2. Parâmetros e Suas Utilidades

Sem parâmetros

#### 3. Exemplo de Requisição

GET -> `api/units`

Body:

```json
{}
```

### Retorno da API

#### Sucesso

Retorna um json contendo uma lista com as unidades da empresa atual e suas informações.

**Ex**:

```json
{
  "Units": [
    {
      "id": 1,
      "company_id": 1,
      "name": "Exemplo 1",
      "acronym": "[EX1]",
      "latitude": "-5.079222",
      "longitude": "-42.761417",
      "created": "2023-07-06T18:35:14-03:00",
      "modified": "2023-07-06T18:35:14-03:00",
      "active": true,
      "deleted": null,
      "is_ticket": false,
      "due_days": 0,
      "created_by": 3,
      "deleted_by": null
    },
    {
      "id": 2,
      "company_id": 1,
      "name": "Exemplo 2",
      "acronym": null,
      "latitude": null,
      "longitude": null,
      "created": "2023-07-06T18:35:14-03:00",
      "modified": "2023-07-06T18:35:14-03:00",
      "active": true,
      "deleted": null,
      "is_ticket": false,
      "due_days": 0,
      "created_by": 3,
      "deleted_by": null
    }
  ],
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando ver as unidades da empresa que participa

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

GET -> `api/units?list_all=basic`

#### 2. Parâmetros e Suas Utilidades

list_all: recebe a palavra `basic` para indicar que a listagem é de apenas o id e o nome das unidades

#### 3. Exemplo de Requisição

GET -> `api/units?list_all=basic`

Body:

```json
{}
```

### Retorno da API

#### Sucesso

Retorna um json contendo uma lista com o id e o nome de cada uma das unidades da empresa atual.
**Ex**:

```json
{
  "Units": {
    "1": "Exemplo 1",
    "2": "Exemplo 2"
  },
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando ver as unidades da empresa que participa

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Você não tem permissão para acessar este recurso."
    }
    ```
