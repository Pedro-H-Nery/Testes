## Working Groups -> Index

### 1. Listagem de todos os grupos de trabalho

### Requisição para API

#### 1. Rota da API

GET-> `api/working-groups`

#### 2. Parâmetros e Suas Utilidades

Sem parâmetros

#### 3. Exemplo de Requisição

GET -> `api/working-groups`

Body:

```json
{}
```

### Retorno da API

#### Sucesso

Retorna um json contendo uma lista com os grupos de trabalho da empresa atual e suas informações.

**Ex**:

```json
{
  "WorkingGroups": [
    {
      "id": 1,
      "company_id": 1,
      "name": "Grupo de Trabalho",
      "description": "Um dos grupos de trabalho ja criados",
      "created": null,
      "modified": "2023-09-11T18:17:54-03:00",
      "deleted": null,
      "created_by": 3,
      "deleted_by": null,
      "users_in_working_groups": [
        {
          "id": 1,
          "working_group_id": 1,
          "user_id": 1,
          "user": {
            "id": 1,
            "unit_id": 1,
            "sector_id": 3,
            "job_id": 3,
            "name": "teste",
            "email": "teste",
            "phone": "7643443667",
            "admission": "1900-12-25",
            "photo_url": "teste.png",
            "company_id": 1,
            "status": true,
            "token": null,
            "active": true,
            "is_visitor": false,
            "company_name": null,
            "created": "2021-11-13T14:32:11-03:00",
            "modified": "2023-08-23T17:48:34-03:00",
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
            "auth_type": 1,
            "calendar_share_code": "teste",
            "deleted": null,
            "is_ticket": true,
            "desactived": null,
            "about": "",
            "linkedin": "",
            "facebook": "",
            "twitter": "",
            "instagram": "",
            "front_cover": null,
            "photo_foreground_url": null,
            "created_by": null,
            "deleted_by": null
          }
        },
        {
          "id": 2,
          "working_group_id": 1,
          "user_id": 3,
          "user": {
            "id": 3,
            "unit_id": 1,
            "sector_id": 1,
            "job_id": 3,
            "name": "teste",
            "email": "teste",
            "phone": "346434523",
            "admission": "2222-01-30",
            "photo_url": "teste.png",
            "company_id": 1,
            "status": true,
            "token": "teste",
            "active": true,
            "is_visitor": false,
            "company_name": null,
            "created": "2022-05-27T14:16:51-03:00",
            "modified": "2023-04-27T11:46:15-03:00",
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
            "deleted_by": null
          }
        }
      ]
    },
    {
      "id": 241,
      "company_id": 1,
      "name": "Grupo 2",
      "description": "",
      "created": "2023-09-11T12:30:31-03:00",
      "modified": "2023-11-17T13:32:43-03:00",
      "deleted": null,
      "created_by": 3,
      "deleted_by": null,
      "users_in_working_groups": [
        {
          "id": 3,
          "working_group_id": 2,
          "user_id": 2,
          "user": {
            "id": 2,
            "unit_id": 1,
            "sector_id": 3,
            "job_id": 11,
            "name": "teste",
            "email": "teste",
            "phone": "543364452",
            "admission": "2000-11-18",
            "photo_url": "teste.png",
            "company_id": 1,
            "status": true,
            "token": "teste",
            "active": true,
            "is_visitor": false,
            "company_name": null,
            "created": "2021-11-13T14:24:18-03:00",
            "modified": "2023-06-23T14:02:52-03:00",
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
            "auth_type": 3,
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
            "deleted_by": null
          }
        },
        {
          "id": 4,
          "working_group_id": 2,
          "user_id": 3,
          "user": {
            "id": 3,
            "unit_id": 1,
            "sector_id": 3,
            "job_id": 3,
            "name": "teste",
            "email": "teste",
            "phone": "5654546354",
            "admission": "2010-10-10",
            "photo_url": "teste.png",
            "company_id": 1,
            "status": true,
            "token": null,
            "active": true,
            "is_visitor": false,
            "company_name": null,
            "created": "2021-11-13T14:32:11-03:00",
            "modified": "2023-08-23T17:48:34-03:00",
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
            "auth_type": 1,
            "calendar_share_code": "teste",
            "deleted": null,
            "is_ticket": true,
            "desactived": null,
            "about": "",
            "linkedin": "",
            "facebook": "",
            "twitter": "",
            "instagram": "",
            "front_cover": null,
            "photo_foreground_url": null,
            "created_by": null,
            "deleted_by": null
          }
        }
      ]
    }
  ],
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário não tiver um nível de permissão igual ou superior a Gestor ou tiver um nível de permissão igual ou superior a Gestor mas estiver tentando visualizar os grupos de trabaho que não são da sua empresa

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Você não tem permissão para acessar este recurso."
    }
    ```

### 2. Listagem com o nome, id e usuários dos grupos de trabalho

### Requisição para API

#### 1. Rota da API

GET -> `api/working-groups?list_all=basic`

#### 2. Parâmetros e Suas Utilidades

list_all: recebe a palavra `basic` para indicar que a listagem é de apenas o id, o nome e os usuários dos grupos de trabalho

#### 3. Exemplo de Requisição

GET -> `api/working-groups?list_all=basic`

Body:

```json
{}
```

### Retorno da API

#### Sucesso

Retorna um json contendo uma lista com o id, o nome e os usuários de cada um dos grupos de trabalho da empresa atual.
**Ex**:

```json
{
  "WorkingGroups": [
    {
      "id": 1,
      "name": "Grupo de Trabalho",
      "users_in_working_groups": [
        {
          "id": 1,
          "working_group_id": 1,
          "user_id": 1,
          "user": {
            "id": 1,
            "name": "teste"
          }
        },
        {
          "id": 2,
          "working_group_id": 1,
          "user_id": 3,
          "user": {
            "id": 3,
            "name": "teste"
          }
        }
      ]
    },
    {
      "id": 2,
      "name": "Grupo 2",
      "users_in_working_groups": [
        {
          "id": 3,
          "working_group_id": 2,
          "user_id": 2,
          "user": {
            "id": 2,
            "name": "teste"
          }
        },
        {
          "id": 4,
          "working_group_id": 2,
          "user_id": 3,
          "user": {
            "id": 3,
            "name": "teste"
          }
        }
      ]
    }
  ],
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário não tiver um nível de permissão igual ou superior a Gestor ou tiver um nível de permissão igual ou superior a Gestor mas estiver tentando visualizar os grupos de trabaho que não são da sua empresa

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Você não tem permissão para acessar este recurso."
    }
    ```
