## Users -> Index

### 1. Listagem de todos os usuários

### Requisição para API

#### 1. Rota da API

GET-> `api/users`

#### 2. Parâmetros e Suas Utilidades

Sem parâmetros

#### 3. Exemplo de Requisição

GET -> `api/users`

Body:

```json
{}
```

### Retorno da API

#### Sucesso

Retorna um json contendo as informações dos usuários combinado com informações da função, setor, unidade e em empresa de cada usuário específico e são divididos baseado na unidade em que pertencem, também as informações das unidades com usuários e de id e nome dos setores e funções e um usuário vazio que pode ser preenchido.

**Ex**:

```json
{
  "users": {
    "Unidade 1": [
      {
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
        "token": "234b2bou32u23b5ou32o4b23uob3k42n3ou4o23b234o23",
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
        "job": null,
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
        "unit": {
          "id": 1,
          "company_id": 1,
          "name": "Unidade 1",
          "acronym": "teste",
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
        "company": {
          "id": 1,
          "plan_id": 1,
          "name": "Empresa 1",
          "corporate_name": "teste",
          "cnpj_cpf": "534234232524",
          "price": "0",
          "recurrency": 12,
          "discount": 100,
          "active": true,
          "created": null,
          "modified": "2023-11-17T12:59:33-03:00",
          "deleted": null,
          "is_users": true,
          "is_forms": true,
          "is_files": true,
          "cusers": true,
          "cep": "79442-344",
          "street": "teste",
          "number": "999",
          "district": "teste",
          "city": "teste",
          "state": "teste",
          "financial_responsible_name": "teste",
          "financial_responsible_cpf_cnpj": "",
          "financial_responsible_telephone": "(44) 98 453-2222",
          "financial_responsible_cep": "24673846",
          "financial_responsible_street": "teste",
          "financial_responsible_number": "222",
          "financial_responsible_district": "teste",
          "financial_responsible_city": "teste",
          "financial_responsible_state": "teste",
          "is_actions": 1,
          "is_meets": 1,
          "is_checklists": 1,
          "is_calendars": 1,
          "is_anomalies": 1,
          "is_tickets": 1,
          "is_trainings": 1,
          "is_projects": 1,
          "is_events": 1,
          "tickets_is_in_sectors": true,
          "unit_by_ajax": false,
          "user_by_ajax": false,
          "action": true,
          "schedule": true,
          "meeting": true,
          "confirmed_meeting": true,
          "stock_update": true,
          "project_summary": false,
          "anomaly_registration": true,
          "schedule_training": true,
          "created_by": null,
          "deleted_by": null,
          "is_file_system": true,
          "work_on_saturday": false,
          "is_georeferencing": true,
          "is_gamefication": true
        }
      },
      {
        "id": 2,
        "unit_id": 1,
        "sector_id": 1,
        "job_id": 1,
        "name": "Usuário 2",
        "email": "teste@gmail.com",
        "phone": "(99)22222-2432",
        "admission": "2031-12-22",
        "photo_url": "teste.jpg",
        "company_id": 1,
        "status": true,
        "token": "234b2bou32u23b5ou32o4b23uob3k42n3ou4o23b234o23",
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
        "job": null,
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
        "unit": {
          "id": 1,
          "company_id": 1,
          "name": "Unidade 1",
          "acronym": "teste",
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
        "company": {
          "id": 1,
          "plan_id": 1,
          "name": "Empresa 1",
          "corporate_name": "teste",
          "cnpj_cpf": "534234232524",
          "price": "0",
          "recurrency": 12,
          "discount": 100,
          "active": true,
          "created": null,
          "modified": "2023-11-17T12:59:33-03:00",
          "deleted": null,
          "is_users": true,
          "is_forms": true,
          "is_files": true,
          "cusers": true,
          "cep": "79442-344",
          "street": "teste",
          "number": "999",
          "district": "teste",
          "city": "teste",
          "state": "teste",
          "financial_responsible_name": "teste",
          "financial_responsible_cpf_cnpj": "",
          "financial_responsible_telephone": "(44) 98 453-2222",
          "financial_responsible_cep": "24673846",
          "financial_responsible_street": "teste",
          "financial_responsible_number": "222",
          "financial_responsible_district": "teste",
          "financial_responsible_city": "teste",
          "financial_responsible_state": "teste",
          "is_actions": 1,
          "is_meets": 1,
          "is_checklists": 1,
          "is_calendars": 1,
          "is_anomalies": 1,
          "is_tickets": 1,
          "is_trainings": 1,
          "is_projects": 1,
          "is_events": 1,
          "tickets_is_in_sectors": true,
          "unit_by_ajax": false,
          "user_by_ajax": false,
          "action": true,
          "schedule": true,
          "meeting": true,
          "confirmed_meeting": true,
          "stock_update": true,
          "project_summary": false,
          "anomaly_registration": true,
          "schedule_training": true,
          "created_by": null,
          "deleted_by": null,
          "is_file_system": true,
          "work_on_saturday": false,
          "is_georeferencing": true,
          "is_gamefication": true
        }
      }
    ]
  },
  "units": [
    {
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
  ],
  "sectors": {
    "1": "Setor 1",
    "2": "Setor 2"
  },
  "jobs": {
    "1": "Função 1",
    "2": "Função 2"
  },
  "user_new": [],
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário não for Master

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Você não tem permissão para acessar este recurso."
    }
    ```
