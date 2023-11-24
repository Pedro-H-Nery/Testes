## Actions -> Delete

### 1. Deletar uma ação

### Requisição para API

#### 1. Rota da API

DELETE -> `api/actions/{Action_id}`

#### 2. Parâmetros e Suas Utilidades

Action_id\*: id da ação que se deseja deletar

#### 3. Exemplo de Requisição

DELETE -> `api/actions/1`

Body:

```json
{}
```

### Retorno da API

#### Sucesso

Retorna um json contendo as informações da ação que foi deletada incluindo informações do projeto, ferramenta de gestão, problema, indicador, reunião, setor e dos usuários responsáveis, em cópia e o usuário que criou a ação e uma mensagem de sucesso.

**Ex**:

```json
{
  "App\\Model\\Entity\\Action": {
    "id": 1,
    "user_id": 3,
    "schedule_id": 1,
    "meet_id": 1,
    "sector_id": 1,
    "indicator_id": 1,
    "managerment_tool_id": 1,
    "company_id": 1,
    "anomaly_id": 1,
    "project_id": 1,
    "status": 3,
    "due_date": "2023-11-28",
    "action": "Ação 1",
    "active": true,
    "end": null,
    "created": "2023-11-24T14:11:01-03:00",
    "modified": "2023-11-24T14:30:50-03:00",
    "done_date": "2023-11-24",
    "rating": 0,
    "deleted": null,
    "created_by": 1,
    "deleted_by": 1
  },
  "message": "Ação deletada com sucesso!",
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário não for Master ou então não for Admin tentando deletar uma ação da empresa que participa ou então o usuário não estiver tentando deletar uma ação que ele é dono

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Você não tem permissão para deletar essa ação!"
    }
    ```

1.  Se acontecer algum erro ao tentar deletar a ação

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Erro ao deletar ação!"
    }
    ```
