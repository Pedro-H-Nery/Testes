## Events -> Edit

### 1. Editar um evento

### Requisição para API

#### 1. Rota da API

PUT -> `api/events/{Event_id}`

#### 2. Parâmetros e Suas Utilidades

Event_id\*: id do evento que se deseja editar.

#### 3. Exemplo de Requisição

PUT -> `api/events/1`

Body:

```json
{
  "name": "Evento 1 Alterado",
  "allday": "0",
  "privacy": "0",
  "start": "2024-11-25T10:11",
  "end": "2024-11-26T12:11",
  "local": "teste",
  "guests": ["2", "3"],
  "working_groups": ["1", "2"],
  "description": "teste",
  "pass": "0",
  "conflicted_init_date": "",
  "conflicted_end_date": ""
}
```

### Retorno da API

#### Sucesso

Retorna um json contendo as informações do evento que foi editado e uma mensagem de sucesso.

**Ex**:

```json
{
  "App\\Model\\Entity\\Event": {
    "id": 1,
    "company_id": 1,
    "user_id": 1,
    "name": "Evento 1 Alterado",
    "start": "2024-11-25T10:11:00-03:00",
    "end": "2024-11-26T12:11:00-03:00",
    "local": "teste",
    "description": "teste",
    "allday": false,
    "privacy": false,
    "created": "2023-11-24T10:33:58-03:00",
    "modified": "2023-11-24T11:44:32-03:00",
    "deleted": null,
    "created_by": 1,
    "deleted_by": null,
    "events_working_groups": [
      {
        "working_group_id": "1",
        "event_id": 1,
        "id": 1
      },
      {
        "working_group_id": "2",
        "event_id": 1,
        "id": 2
      }
    ],
    "events_guests": [
      {
        "user_id": "2",
        "event_id": 1
      },
      {
        "user_id": "3",
        "event_id": 1
      }
    ]
  },
  "message": "Sucesso ao editar Compromisso!",
  "status": 1
}
```

OBS: [Pode causar conflito](../AdditionalContent/Conflict.md) com outros compromissos ou reuniões.

#### Erro(s)

1.  Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando editar um compromisso não privado de um usuário da empresa que participa ou então não estiver tentando editar um compromisso que ele criou

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Você não tem permissão para acessar este recurso."
    }
    ```

2.  Se o compromisso passado como parâmetro não for encontrado

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Registro não encontrado!"
    }
    ```

3.  Se a data de início do compromisso for maior que a data de fim

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "A data de início precisa ser antes da data de fim."
    }
    ```

4.  Se acontecer algum erro ao tentar salvar o compromisso

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Erro ao editar Compromisso!"
    }
    ```
