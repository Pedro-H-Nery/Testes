## Working Groups -> Delete

### 1. Deletar um grupo de trabalho

### Requisição para API

#### 1. Rota da API

DELETE -> `api/working-groups/{Working_Group_id}`

#### 2. Parâmetros e Suas Utilidades

Working_Group_id\*: o id do grupo de trabalho que será deletado

#### 3. Exemplo de Requisição

DELETE -> `api/working-groups/1`

Body:

```json
{}
```

### Retorno da API

#### Sucesso

Retorna um json contendo as informações do grupo de trabalho que foi deletado e uma mensagem de sucesso.

**Ex**:

```json
{
  "App\\Model\\Entity\\WorkingGroup": {
    "id": 1,
    "company_id": 1,
    "name": "Grupo de Trabalho Alterado",
    "description": "",
    "created": "2023-11-17T13:13:34-03:00",
    "modified": "2023-11-17T13:23:25-03:00",
    "deleted": null,
    "created_by": 3,
    "deleted_by": 3
  },
  "message": "Sucesso ao deletar Grupo de Trabalho!",
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário não tiver um nível de permissão igual ou superior a Gestor ou tiver um nível de permissão igual ou superior a Gestor mas estiver tentando editar um grupo de trabaho que não é da sua empresa

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Você não tem permissão para acessar esse recurso!"
    }
    ```

2.  Se acontecer algum erro ao tentar deletar o grupo de trabalho passado como parâmetro

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Erro ao deletar Grupo de Trabalho!"
    }
    ```
