## Events -> Index

### 1. Ver a agenda de um usuário específico

### Requisição para API

#### 1. Rota da API

GET-> `api/events`

GET-> `api/events/{User_id}`

GET-> `api/events?share={Código}`

#### 2. Parâmetros e Suas Utilidades

User_id: id do usuário que se deseja ver a agenda. Se não for especificado será retornada a agenda do usuário atual.

share: código de compartilhamento da agenda de um usuário. Se não for especificado será retornada a agenda do usuário atual.

#### 3. Exemplo de Requisição

GET-> `api/events`

GET-> `api/events/2`

GET-> `api/events?share=o2uho23uo5h2o4h343u24h32h`

Body:

```json
{}
```

### Retorno da API

#### Sucesso

Retorna um json contendo as informações do usuário específicado/usuário atual onde o usuário possui um array indicando os ompromissos, reuniões, ausências, ações, chamados, formações e tarefas antigas e ainda não realizadas da rotina produtiva associadas a ele, o título da agenda que muda se for o usuário atual ou outro usuário, todos eventos associados a ele divididos em compromissos, reuniões, ausências, ações, chamados, formações e tarefas antigas e ainda não realizadas da rotina produtiva e o atributo `Multiview` que especifica se a agenda é de um ou de vários usuários.

**Ex**:

```json
{
  "Users": {
    "2": {
      "id": 2,
      "unit_id": 1,
      "sector_id": 223,
      "job_id": 2,
      "name": "Usuário 2",
      "email": "usuario2@gmail.com",
      "phone": "(88)99999-6666",
      "admission": "2020-10-20",
      "photo_url": "usuario2.png",
      "company_id": 1,
      "status": true,
      "token": null,
      "active": true,
      "is_visitor": false,
      "company_name": null,
      "created": "2022-05-14T08:44:40-03:00",
      "modified": "2022-05-17T09:04:35-03:00",
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
      "events": [],
      "schedules": [1, 2],
      "holidays": [],
      "actions": [],
      "tickets": [],
      "trainings": ["45 - 48"],
      "tasks": [],
      "pastTasks": []
    }
  },
  "Title": "Agenda de Usuário 2",
  "All_Events": {
    "Events": [],
    "Schedules": {
      "1": {
        "id": 1,
        "meet_id": 1,
        "company_id": 1,
        "name": "teste",
        "local": null,
        "date": "2023-05-18T23:21:00-03:00",
        "message": null,
        "resume": null,
        "status": 1,
        "confirmed": true,
        "inited": true,
        "init": "2023-05-26T11:10:35-03:00",
        "type": 2,
        "link": "teste.com",
        "file_path": null,
        "end": "2023-05-26T11:15:29-03:00",
        "active": null,
        "created": null,
        "modified": null,
        "deleted": null,
        "created_by": null,
        "deleted_by": null,
        "guests": [],
        "meet": {
          "id": 1,
          "unit_id": 1,
          "frequency_id": 1,
          "user_id": 1,
          "company_id": 1,
          "name": "teste",
          "local": null,
          "duration": "00:01:00",
          "ruling_path": null,
          "notification": true,
          "initial": true,
          "active": true,
          "created": "2023-05-18T18:22:11-03:00",
          "modified": "2023-05-26T11:10:17-03:00",
          "deleted": null,
          "created_by": null,
          "deleted_by": null,
          "participants": [
            {
              "user_id": 1,
              "meet_id": 1,
              "created": "2023-05-26T11:10:17-03:00",
              "modified": "2023-05-26T11:10:17-03:00",
              "created_by": null,
              "deleted_by": null
            },
            {
              "user_id": 2,
              "meet_id": 1,
              "created": "2023-05-26T11:10:17-03:00",
              "modified": "2023-05-26T11:10:17-03:00",
              "created_by": null,
              "deleted_by": null
            }
          ],
          "unit": {
            "id": 1,
            "company_id": 1,
            "name": "Unidade 1",
            "acronym": "[Un1]",
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
          }
        },
        "_matchingData": {
          "Meets": {
            "id": 1,
            "unit_id": 1,
            "frequency_id": 1,
            "user_id": 2,
            "company_id": 1,
            "name": "teste",
            "local": null,
            "duration": "00:01:00",
            "ruling_path": null,
            "notification": true,
            "initial": true,
            "active": true,
            "created": "2023-05-18T18:22:11-03:00",
            "modified": "2023-05-26T11:10:17-03:00",
            "deleted": null,
            "created_by": null,
            "deleted_by": null
          }
        },
        "members": [2]
      },
      "2": {
        "id": 2,
        "meet_id": 2,
        "company_id": 1,
        "name": "teste",
        "local": null,
        "date": "2023-10-04T00:40:00-03:00",
        "message": "",
        "resume": null,
        "status": 1,
        "confirmed": true,
        "inited": true,
        "init": "2023-09-29T14:00:00-03:00",
        "type": 1,
        "link": "",
        "file_path": null,
        "end": "2023-09-29T14:11:00-03:00",
        "active": null,
        "created": "2023-09-29T00:40:51-03:00",
        "modified": "2023-09-29T14:11:13-03:00",
        "deleted": null,
        "created_by": 2,
        "deleted_by": null,
        "guests": [
          {
            "user_id": 3,
            "schedule_id": 2,
            "created": "2023-09-29T14:02:09-03:00",
            "modified": "2023-09-29T14:02:09-03:00",
            "created_by": null,
            "deleted_by": null
          },
          {
            "user_id": 4,
            "schedule_id": 2,
            "created": "2023-09-29T14:02:09-03:00",
            "modified": "2023-09-29T14:02:09-03:00",
            "created_by": null,
            "deleted_by": null
          }
        ],
        "meet": {
          "id": 2,
          "unit_id": 1,
          "frequency_id": 1,
          "user_id": 1,
          "company_id": 1,
          "name": "teste",
          "local": "teste",
          "duration": "00:30:00",
          "ruling_path": null,
          "notification": true,
          "initial": true,
          "active": true,
          "created": "2023-06-30T16:38:25-03:00",
          "modified": "2023-09-18T13:12:44-03:00",
          "deleted": null,
          "created_by": 1,
          "deleted_by": null,
          "participants": [
            {
              "user_id": 1,
              "meet_id": 2,
              "created": "2023-09-18T13:12:44-03:00",
              "modified": "2023-09-18T13:12:44-03:00",
              "created_by": null,
              "deleted_by": null
            },
            {
              "user_id": 2,
              "meet_id": 2,
              "created": "2023-09-18T13:12:44-03:00",
              "modified": "2023-09-18T13:12:44-03:00",
              "created_by": null,
              "deleted_by": null
            }
          ],
          "unit": {
            "id": 1,
            "company_id": 1,
            "name": "Unidade 1",
            "acronym": "[Un1]",
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
          }
        },
        "_matchingData": {
          "Meets": {
            "id": 2,
            "unit_id": 1,
            "frequency_id": 1,
            "user_id": 1,
            "company_id": 1,
            "name": "teste 2",
            "local": "teste",
            "duration": "00:30:00",
            "ruling_path": null,
            "notification": true,
            "initial": true,
            "active": true,
            "created": "2023-06-30T16:38:25-03:00",
            "modified": "2023-09-18T13:12:44-03:00",
            "deleted": null,
            "created_by": 1,
            "deleted_by": null
          }
        },
        "members": [2]
      }
    },
    "Holidays": [],
    "Actions": [],
    "Tickets": [],
    "Trainings": {
      "1 - 2": {
        "test_schedule_id": 1,
        "user_id": 2,
        "training_date_init": null,
        "training_date_end": null,
        "test_date_init": null,
        "test_date_end": null,
        "status": 0,
        "points": null,
        "attendance": 0,
        "reason": null,
        "created": "2023-10-08T20:49:25-03:00",
        "modified": "2023-10-08T20:49:25-03:00",
        "deleted": null,
        "created_by": null,
        "deleted_by": null,
        "test_schedule": {
          "id": 1,
          "company_id": 1,
          "test_id": null,
          "training_id": 1,
          "unit_id": 1,
          "job_id": null,
          "sector_id": null,
          "type": 0,
          "name_of_teacher": "",
          "local": "",
          "date_start": "2023-10-05",
          "date_end": "2023-10-25",
          "training_init": null,
          "training_end": null,
          "hours": "00:00:00",
          "goal_participants": null,
          "method_id": null,
          "created": "2023-10-08T20:49:25-03:00",
          "modified": "2023-10-08T20:50:47-03:00",
          "deleted": null,
          "created_by": 3,
          "deleted_by": null,
          "training": {
            "id": 1,
            "company_id": 1,
            "user_id": 2,
            "unit_id": 1,
            "name": "Formaçao 1",
            "type": 0,
            "workload": 80,
            "name_of_teacher": null,
            "local": null,
            "movie": "",
            "training_path": null,
            "description": "",
            "created": "2023-06-16T16:42:34-03:00",
            "modified": "2023-06-16T16:42:34-03:00",
            "deleted": null,
            "created_by": null,
            "deleted_by": null,
            "unit": {
              "id": 1,
              "company_id": 1,
              "name": "Unidade 1",
              "acronym": "[Un1]",
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
            }
          }
        },
        "members": [2]
      }
    },
    "PastTasks": [],
    "Tasks": []
  },
  "Multiview": false,
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário estiver tentando ver a agenda de outro usuário mas o usuário que se deseja ver a agenda não for encontrado

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Não há usuários para exibir."
    }
    ```

### 2. Ver a agenda mesclada de vários usuários

### Requisição para API

#### 1. Rota da API

GET-> `api/events/{User_id},{User_id},{User_id}`

GET-> `api/events?sector_id_view={Sector_id}`

GET-> `api/events?working_group_id_view={Working_Group_id}`

GET-> `api/events?unit_id_view={Unit_id}`

GET-> `api/events?job_id_view={Job_id}`

#### 2. Parâmetros e Suas Utilidades

User_id\*: ids dos usuários separado por vírgula que se deseja ver a agenda mesclada;

sector_id_view: id do setor que se deseja ver a agenda mesclada dos usuários desse setor;

working_group_id_view: id do grupo de trabalho que se deseja ver a agenda mesclada dos usuários desse grupo de trabalho;

unit_id_view: id da unidade que se deseja ver a agenda mesclada dos usuários dessa unidade;

job_id_view: id da função que se deseja ver a agenda mesclada dos usuários dessa função.

#### 3. Exemplo de Requisição

GET-> `api/events/5,6`

GET-> `api/events?sector_id_view=1`

GET-> `api/events?working_group_id_view=1`

GET-> `api/events?unit_id_view=1`

GET-> `api/events?job_id_view=1`

Body:

```json
{}
```

### Retorno da API

#### Sucesso

Retorna um json contendo as informações de cada um dos usuários específicados ou dos usuários de um setor, grupo de trabalho ou função ou unidade onde cada usuário possui um array que indica os compromissos, reuniões e ausências relacionadas a ele, o título da agenda, todos eventos associados a esses usuários divididos em compromissos, reuniões e ausências e mesclados entre todos os usuários e o atributo `Multiview` que especifica se a agenda é de um ou de vários usuários.

**Ex**:

```json
{
  "Users": {
    "5": {
      "id": 5,
      "unit_id": 1,
      "sector_id": 4,
      "job_id": 3,
      "name": "Usuário 5",
      "email": "usuario5@gmail.com",
      "phone": "324324325",
      "admission": "2020-11-01",
      "photo_url": "semfoto.png",
      "company_id": 1,
      "status": true,
      "token": null,
      "active": true,
      "is_visitor": false,
      "company_name": null,
      "created": "2023-05-17T17:50:39-03:00",
      "modified": "2023-07-03T16:59:20-03:00",
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
      "auth_type": 2,
      "calendar_share_code": "343465ygefve54tc2r2xr2t24tc",
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
      "events": [],
      "schedules": [],
      "holidays": []
    },
    "6": {
      "id": 6,
      "unit_id": 1,
      "sector_id": 4,
      "job_id": 3,
      "name": "Usuário 6",
      "email": "usuario6@gmail.com",
      "phone": "6342465645",
      "admission": "2001-11-01",
      "photo_url": "semfoto.png",
      "company_id": 1,
      "status": true,
      "token": "n6bect54yvv6ucr5ct645x2r24y54u46cu",
      "active": true,
      "is_visitor": false,
      "company_name": null,
      "created": "2023-05-17T17:50:39-03:00",
      "modified": "2023-08-15T16:44:40-03:00",
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
      "calendar_share_code": "3c478x4y6yc426y3xry428yr82r2x",
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
      "events": [],
      "schedules": [],
      "holidays": []
    }
  },
  "Title": "Agenda",
  "All_Events": {
    "Events": {},
    "Schedules": {},
    "Holidays": []
  },
  "Multiview": true,
  "status": 1
}
```

#### Erro(s)

1.  Se nenhum usuário for encontrado para mostrar a agenda

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Não há usuários para exibir."
    }
    ```
