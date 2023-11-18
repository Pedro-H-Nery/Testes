## Working Groups -> Add

### 1. Adicionar novo grupo de trabalho

### Requisição para API

#### 1. Rota da API

POST -> `api/working-groups`

#### 2. Parâmetros e Suas Utilidades

Sem parâmetros

#### 3. Exemplo de Requisição

POST -> `api/working-groups`

Body:

```json
{
  "name": "Grupo de Trabalho",
  "description": "Um dos grupos de trabalho ja criados",
  "users": ["1", "2"]
}
```

OBS: os atributos `name` e `users` são obrigatórios e `description` é opcional.

### Retorno da API

#### Sucesso

Retorna um json contendo as informações do grupo de trabalho que foi criado e uma mensagem de sucesso.

**Ex**:

```json
{
  "App\\Model\\Entity\\WorkingGroup": {
    "name": "Grupo de Trabalho",
    "description": "Um dos grupos de trabalho ja criados",
    "users_in_working_groups": [
      {
        "user_id": 1,
        "working_group_id": 1,
        "id": 1
      },
      {
        "user_id": 2,
        "working_group_id": 1,
        "id": 2
      }
    ],
    "company_id": 1,
    "created": "2023-11-17T13:13:34-03:00",
    "modified": "2023-11-17T13:13:34-03:00",
    "created_by": 3,
    "id": 1
  },
  "message": "Sucesso ao adicionar Grupo de Trabalho!",
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário não tiver um nível de permissão igual ou superior a Gestor

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Você não tem permissão para acessar este recurso."
    }
    ```

2.  Se acontecer algum erro ao tentar salvar o grupo de trabalho

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Erro ao adicionar Grupo de Trabalho."
    }
    ```
