## Actions -> Add

### 1. Adicionar nova ação

### Requisição para API

#### 1. Rota da API

POST -> `api/actions`

#### 2. Parâmetros e Suas Utilidades

Sem parâmetros

#### 3. Exemplo de Requisição

POST -> `api/actions`

Body:

```json
{
  "remmember": "0",
  "action": "Ação 1",
  "responsibles": "1",
  "due_date": "2023-11-28",
  "sector_id": "1",
  "meet_id": "1",
  "schedule_id": "1",
  "in_copies": ["2", "3"],
  "project_id": "1",
  "anomaly_id": "1",
  "indicator_id": "1",
  "managerment_tool_id": "1",
  "adicionar": "adicionar",
  "attachments": []
}
```

OBS: os atributos `remmember`, `action`, `responsibles`, `due_date`, `sector_id`, `adicionar` e `attachments` são obrigatórios e os outros são opcionais.

### Retorno da API

#### Sucesso

Retorna um json contendo as informações da ação que foi criada incluindo informações do projeto, ferramenta de gestão, problema, indicador, reunião, setor e dos usuários responsáveis, em cópia e o usuário que criou a ação e uma mensagem de sucesso.

**Ex**:

```json
{
  "App\\Model\\Entity\\Action": {
    "id": 1,
    "user_id": 1,
    "schedule_id": 1,
    "meet_id": 1,
    "sector_id": 1,
    "indicator_id": 1,
    "managerment_tool_id": 1,
    "company_id": 1,
    "anomaly_id": 1,
    "project_id": 1,
    "status": 2,
    "due_date": "2023-11-28",
    "action": "Ação 1",
    "active": true,
    "end": null,
    "created": "2023-11-24T14:01:13-03:00",
    "modified": "2023-11-24T14:01:13-03:00",
    "done_date": null,
    "rating": 0,
    "deleted": null,
    "created_by": 1,
    "deleted_by": null,
    "atachments": [],
    "project": {
      "id": 1,
      "company_id": 1,
      "unit_id": 1,
      "user_id": 1,
      "name": "Projeto 1",
      "description": "",
      "priority": 1,
      "active": true,
      "created": null,
      "modified": null,
      "deleted": null,
      "created_by": null,
      "deleted_by": null
    },
    "managerment_tool": {
      "id": 1,
      "name": "Ferramenta de Gestão 1",
      "deleted": null,
      "active": true,
      "created": "2022-09-16T16:00:22-03:00",
      "modified": "2022-09-16T16:00:22-03:00",
      "company_id": 1,
      "created_by": null,
      "deleted_by": null
    },
    "anomaly": {
      "id": 1,
      "company_id": 1,
      "sector_id": 1,
      "anomalie_couse_id": 2,
      "user_id": 1,
      "unit_id": 1,
      "unit_ticket_id": null,
      "sector_ticket_id": null,
      "ticket_id": null,
      "name": "Problema 1",
      "active": false,
      "created": "2022-01-24T10:40:14-03:00",
      "modified": "2022-05-14T08:56:40-03:00",
      "date": "2022-01-21",
      "description": "",
      "probable_couses": "teste",
      "probable_solutions": "teste",
      "status": true,
      "photo": "Não",
      "date_resolve": null,
      "deleted": null,
      "created_by": null,
      "resolved_by": null,
      "deleted_by": null
    },
    "indicator": {
      "id": 1,
      "deleted": null,
      "name": "Indicador 1",
      "active": false,
      "created": "2021-12-01T23:11:02-03:00",
      "company_id": 1,
      "modified": "2021-12-08T20:02:25-03:00",
      "created_by": null,
      "deleted_by": null
    },
    "meet": {
      "id": 1,
      "unit_id": 1,
      "frequency_id": 2,
      "user_id": 1,
      "company_id": 1,
      "name": "Reunião 1",
      "local": null,
      "duration": "00:30:00",
      "ruling_path": "teste.pdf",
      "notification": true,
      "initial": true,
      "active": true,
      "created": "2021-11-19T12:05:54-03:00",
      "modified": "2023-05-02T07:10:46-03:00",
      "deleted": null,
      "created_by": null,
      "deleted_by": null
    },
    "user": {
      "id": 1,
      "unit_id": 1,
      "sector_id": 1,
      "job_id": 1,
      "name": "Usuário 1",
      "email": "teste@gmail.com",
      "phone": "(99)22222-2432",
      "admission": "2031-12-22",
      "photo_url": "teste.jpg",
      "company_id": 1,
      "status": true,
      "token": null,
      "active": true,
      "is_visitor": false,
      "company_name": null,
      "created": "2021-11-13T14:32:11-03:00",
      "modified": "2023-11-24T09:37:33-03:00",
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
      "calendar_share_code": "645c35y45xc54yb64b45c34cgtrhte4",
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
    },
    "sector": {
      "id": 1,
      "company_id": 1,
      "name": "Setor 1",
      "acronym": null,
      "is_ticket": true,
      "active": true,
      "due_days": 100,
      "created": null,
      "modified": "2023-06-27T18:19:36-03:00",
      "deleted": null,
      "created_by": null,
      "deleted_by": null
    },
    "comments": [],
    "in_copies": [
      {
        "user_id": 2,
        "action_id": 1
      },
      {
        "user_id": 3,
        "action_id": 1
      }
    ],
    "responsibles": [
      {
        "user_id": 1,
        "action_id": 1
      }
    ]
  },
  "message": {
    "message": "Ação cadastrada com sucesso!",
    "points_message": "Você ganhou 1 pontos! Agora você possui 1 pontos",
    "points": 1,
    "total": 1,
    "error": ""
  },
  "status": 1
}
```

OBS: [Pode gerar pontos](../AdditionalContent/GameficationPoints.md).

Se a empresa não possui gameficação então no atributo `message` estará apenas a mensagem de sucesso que está no atributo `message` de `message`.

#### Erro(s)

1.  Se acontecer algum erro ao tentar salvar a ação

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Erro ao cadastrar ação!"
    }
    ```
