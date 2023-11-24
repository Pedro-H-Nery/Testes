## Events -> Add

### 1. Adicionar novo evento

### Requisição para API

#### 1. Rota da API

POST -> `api/events`

#### 2. Parâmetros e Suas Utilidades

Sem parâmetros

#### 3. Exemplo de Requisição

POST -> `api/events`

Body:

```json
{
  "name": "Evento 1",
  "allday": "0",
  "privacy": "0",
  "start": "2023-11-25T10:11",
  "end": "2023-11-26T12:11",
  "local": "teste",
  "guests": ["2", "3"],
  "working_groups": ["1", "2"],
  "description": "",
  "pass": "0",
  "conflicted_init_date": "",
  "conflicted_end_date": ""
}
```

### Retorno da API

#### Sucesso

Retorna um json contendo as informações do evento que foi criado e uma mensagem de sucesso.

**Ex**:

```json
{
  "App\\Model\\Entity\\Event": {
    "name": "Evento 1",
    "allday": false,
    "privacy": false,
    "start": "2023-11-25T10:11:00-03:00",
    "end": "2023-11-26T12:11:00-03:00",
    "local": "teste",
    "description": "",
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
    "company_id": 1,
    "user_id": 1,
    "events_guests": [
      {
        "user_id": "2",
        "event_id": 1
      },
      {
        "user_id": "3",
        "event_id": 1
      }
    ],
    "created": "2023-11-24T10:13:34-03:00",
    "modified": "2023-11-24T10:13:34-03:00",
    "created_by": 1,
    "id": 1
  },
  "message": {
    "message": "Sucesso ao adicionar Compromisso!",
    "points_message": "Você ganhou 2 pontos! Agora você possui 2 pontos",
    "points": 2,
    "total": 2,
    "error": ""
  },
  "status": 1
}
```

OBS: [Pode causar conflito](../AdditionalContent/Conflict.md) com outros compromissos ou reuniões.

[Pode gerar pontos](../AdditionalContent/GameficationPoints.md).

Se a empresa não possui gameficação então no atributo `message` estará apenas a mensagem de sucesso que está no atributo `message` de `message`.

#### Erro(s)

1.  Se a data de início do compromisso for maior que a data de fim

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "A data de início precisa ser antes da data de fim."
    }
    ```

2.  Se acontecer algum erro ao tentar salvar o compromisso

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Erro ao adicionar Compromisso!"
    }
    ```
