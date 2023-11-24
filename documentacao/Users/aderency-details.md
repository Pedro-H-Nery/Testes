## Users -> Aderency Details

### 1. Ver a produtividade detalhada de um usuário

### Requisição para API

#### 1. Rota da API

GET -> `api/users/aderency-details/{User_id}`

#### 2. Parâmetros e Suas Utilidades

User_id\*: id do usuário que se deseja ver a produtividade detalhada

#### 3. Exemplo de Requisição

GET -> `api/users/aderency-details/1`

Body:

```json
{}
```

### Retorno da API

#### Sucesso

Retorna um json contendo as informações do usuário passado como parâmetro, informações da função, do setor e da unidade do usuário, as informações das reuniões e das ações associadas ao usuário, informações da última atividade feita pelo usuário no sistema e informações de cada uma das rotinas produtivas feitas pelo usuário.

**Ex**:

```json
{
  "user": {
    "id": 1,
    "unit_id": 1,
    "sector_id": 1,
    "job_id": 1,
    "name": "Usuário 1",
    "email": "teste@gmail.com",
    "phone": "(88)99999-6666",
    "admission": "2001-12-01",
    "photo_url": "teste.jpg",
    "company_id": 1,
    "status": true,
    "token": "rwrtcu349347yemt8yyxr64t6tx36t8m6cy34ym3xm8z",
    "active": true,
    "is_visitor": false,
    "company_name": null,
    "created": "2021-11-13T14:22:08-03:00",
    "modified": "2023-06-23T14:05:36-03:00",
    "is_actions": 1,
    "is_meets": 1,
    "is_checklists": 1,
    "is_forms": 1,
    "is_calendars": 1,
    "is_anomalies": 1,
    "is_tickets": 1,
    "is_trainings": 1,
    "is_users": 1,
    "is_files": 1,
    "is_events": 1,
    "auth_type": 5,
    "calendar_share_code": null,
    "deleted": null,
    "is_ticket": true,
    "desactived": null,
    "about": null,
    "linkedin": null,
    "facebook": null,
    "twitter": null,
    "instagram": null,
    "front_cover": null,
    "photo_foreground_url": null,
    "created_by": null,
    "deleted_by": null,
    "unit": {
      "id": 1,
      "company_id": 1,
      "name": "teste",
      "acronym": "[teste]",
      "latitude": null,
      "longitude": null,
      "created": null,
      "modified": "2023-10-20T15:37:40-03:00",
      "active": true,
      "deleted": null,
      "is_ticket": true,
      "due_days": 25,
      "created_by": null,
      "deleted_by": null
    },
    "sector": {
      "id": 1,
      "company_id": 1,
      "name": "teste",
      "acronym": null,
      "is_ticket": false,
      "active": true,
      "due_days": null,
      "created": null,
      "modified": "2022-05-14T08:46:02-03:00",
      "deleted": null,
      "created_by": null,
      "deleted_by": null
    },
    "job": null,
    "meets": [
      {
        "id": 1,
        "unit_id": 1,
        "frequency_id": 1,
        "user_id": 1,
        "company_id": 1,
        "name": "teste",
        "local": null,
        "duration": "00:35:00",
        "ruling_path": null,
        "notification": true,
        "initial": true,
        "active": true,
        "created": "2023-05-18T18:20:59-03:00",
        "modified": "2023-05-26T10:43:51-03:00",
        "deleted": null,
        "created_by": null,
        "deleted_by": null,
        "aderency": 100,
        "completed_actions": 0,
        "on_going_actions": 0,
        "past_actions": 0
      }
    ],
    "past_actions": [
      {
        "id": 1,
        "user_id": 1,
        "schedule_id": null,
        "meet_id": null,
        "sector_id": 1,
        "indicator_id": null,
        "managerment_tool_id": null,
        "company_id": 1,
        "anomaly_id": null,
        "project_id": null,
        "status": 1,
        "due_date": "2023-05-12",
        "action": "acao 1",
        "active": true,
        "end": null,
        "created": "2023-05-09T22:01:31-03:00",
        "modified": "2023-05-13T00:00:01-03:00",
        "done_date": null,
        "rating": 0,
        "deleted": null,
        "created_by": null,
        "deleted_by": null
      }
    ],
    "on_going_actions": [],
    "completed_actions": [],
    "actions": [
      {
        "id": 1,
        "user_id": 1,
        "schedule_id": null,
        "meet_id": null,
        "sector_id": 1,
        "indicator_id": null,
        "managerment_tool_id": null,
        "company_id": 1,
        "anomaly_id": null,
        "project_id": null,
        "status": 1,
        "due_date": "2023-05-12",
        "action": "acao 1",
        "active": true,
        "end": null,
        "created": "2023-05-09T22:01:31-03:00",
        "modified": "2023-05-13T00:00:01-03:00",
        "done_date": null,
        "rating": 0,
        "deleted": null,
        "created_by": null,
        "deleted_by": null
      }
    ],
    "last_log": {
      "id": 1,
      "user_id": 1,
      "company_id": 1,
      "unit_id": 1,
      "controller": "Dashboard",
      "action": "dash",
      "params": null,
      "data": null,
      "created": "2023-05-16T17:28:09-03:00",
      "modified": "2023-05-16T17:28:09-03:00"
    },
    "calendars_report": {
      "2023-07": {
        "ano": "2023",
        "mes": "07",
        "aderencia": 0
      },
      "2023-08": {
        "ano": "2023",
        "mes": "08",
        "aderencia": 63
      }
    }
  },
  "status": 1
}
```

#### Erro(s)

Não possui erros possíveis.
