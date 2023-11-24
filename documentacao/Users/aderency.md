## Users -> Aderency

### 1. Ver a produtividade dos usuários

### Requisição para API

#### 1. Rota da API

GET -> `api/users/aderency`

#### 2. Parâmetros e Suas Utilidades

Sem parâmetros

#### 3. Exemplo de Requisição

GET -> `api/users/aderency`

Body:

```json
{}
```

### Retorno da API

#### Sucesso

Retorna um json contendo as informações dos usuários da unidade atual, as informações das ações atrasadas, em andamento e concluidas por cada usuário, as informações de todas as ações relacionadas ao usuário, a ultima atividade do usuário no sistema e também um valor de produtividade associado a reuniões que o usuário participou.

**Ex**:

```json
{
  "users": [
    {
      "id": 1,
      "unit_id": 1,
      "sector_id": 1,
      "job_id": 3,
      "name": "Usuário 1",
      "email": "teste@gmail.com",
      "phone": "(88)88888-8888",
      "admission": "2041-01-01",
      "photo_url": "teste.jpg",
      "company_id": 1,
      "status": true,
      "token": "432inio4i52ip3boib1bv2yv31iy2v312iy4v1i4oi1i443534i5oh5",
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
      "aderency": 75
    },
    {
      "id": 2,
      "unit_id": 1,
      "sector_id": 1,
      "job_id": 1,
      "name": "Usuário 2",
      "email": "usuario2@gmail.com",
      "phone": "(77)88888-9999",
      "admission": "1906-09-04",
      "photo_url": "usuario2.png",
      "company_id": 1,
      "status": true,
      "token": "tvv3hc3tm75m3tc34ymym438c7x344n674t6nq6x27rxo28rxn23",
      "active": true,
      "is_visitor": false,
      "company_name": null,
      "created": "2022-02-08T20:21:32-03:00",
      "modified": "2023-03-13T10:00:31-03:00",
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
      "is_events": 0,
      "auth_type": 5,
      "calendar_share_code": null,
      "deleted": null,
      "is_ticket": false,
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
      "past_actions": [
        {
          "id": 2,
          "user_id": 2,
          "schedule_id": null,
          "meet_id": null,
          "sector_id": 1,
          "indicator_id": null,
          "managerment_tool_id": null,
          "company_id": 1,
          "anomaly_id": null,
          "project_id": 1,
          "status": 1,
          "due_date": "2020-01-25",
          "action": "acao 2",
          "active": true,
          "end": null,
          "created": "2022-07-30T11:24:09-03:00",
          "modified": "2022-08-17T15:00:29-03:00",
          "done_date": null,
          "rating": 0,
          "deleted": null,
          "created_by": null,
          "deleted_by": null
        }
      ],
      "on_going_actions": [],
      "completed_actions": [
        {
          "id": 3,
          "user_id": 15,
          "schedule_id": null,
          "meet_id": null,
          "sector_id": 23,
          "indicator_id": null,
          "managerment_tool_id": null,
          "company_id": 1,
          "anomaly_id": null,
          "project_id": 27,
          "status": 3,
          "due_date": "2024-02-12",
          "action": "acao 3",
          "active": true,
          "end": null,
          "created": "2022-08-08T09:52:40-03:00",
          "modified": "2023-03-10T13:35:14-03:00",
          "done_date": "2023-03-10",
          "rating": 0,
          "deleted": null,
          "created_by": null,
          "deleted_by": null
        }
      ],
      "actions": [
        {
          "id": 2,
          "user_id": 2,
          "schedule_id": null,
          "meet_id": null,
          "sector_id": 1,
          "indicator_id": null,
          "managerment_tool_id": null,
          "company_id": 1,
          "anomaly_id": null,
          "project_id": 1,
          "status": 1,
          "due_date": "2020-01-25",
          "action": "acao 2",
          "active": true,
          "end": null,
          "created": "2022-07-30T11:24:09-03:00",
          "modified": "2022-08-17T15:00:29-03:00",
          "done_date": null,
          "rating": 0,
          "deleted": null,
          "created_by": null,
          "deleted_by": null
        },
        {
          "id": 3,
          "user_id": 2,
          "schedule_id": null,
          "meet_id": null,
          "sector_id": 1,
          "indicator_id": null,
          "managerment_tool_id": null,
          "company_id": 1,
          "anomaly_id": null,
          "project_id": 1,
          "status": 3,
          "due_date": "2024-02-12",
          "action": "acao 3",
          "active": true,
          "end": null,
          "created": "2022-08-08T09:52:40-03:00",
          "modified": "2023-03-10T13:35:14-03:00",
          "done_date": "2023-03-10",
          "rating": 0,
          "deleted": null,
          "created_by": null,
          "deleted_by": null
        }
      ],
      "last_log": {
        "id": 2,
        "user_id": 2,
        "company_id": 1,
        "unit_id": 1,
        "controller": "Dashboard",
        "action": "dash",
        "params": null,
        "data": null,
        "created": "2023-05-15T15:10:55-03:00",
        "modified": "2023-05-15T15:10:55-03:00"
      },
      "aderency": 33.33333333333333
    }
  ],
  "status": 1
}
```

#### Erro(s)

Não possui erros possíveis.
