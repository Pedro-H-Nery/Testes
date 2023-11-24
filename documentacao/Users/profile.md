## Users -> Profile

### 1. Ver o perfil de um usuário

### Requisição para API

#### 1. Rota da API

GET -> `api/users/profile/{User_id}`

#### 2. Parâmetros e Suas Utilidades

User_id\*: id do usuário que se deseja ver o perfil

#### 3. Exemplo de Requisição

GET -> `api/users/profile/1`

Body:

```json
{}
```

### Retorno da API

#### Sucesso

Retorna um json contendo as informações do usuário passado como parâmetro e da função e do setor do usuário.

**Ex**:

```json
{
  "user": {
    "id": 1,
    "unit_id": 1,
    "sector_id": 1,
    "job_id": 3,
    "name": "Usuário 1",
    "email": "teste@gmail.com",
    "phone": "(88)99999-66666",
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
    "job": null
  },
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário não for Master ou então não tiver um nível de permissão igual ou superior a Gestor e estiver tentando ver o perfil de um usuário da empresa que participa ou não estiver tentando ver o próprio perfil

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Você não tem permissão para acessar este recurso."
    }
    ```
