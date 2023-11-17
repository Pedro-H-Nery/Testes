## Companies -> Index

### 1. Listagem da empresas

### Requisição para API

#### 1. Rota da API

GET -> `api/companies`

#### 2. Parâmetros e Suas Utilidades

Sem parâmetros

#### 3. Exemplo de Requisição

GET -> `api/companies`

Body:

```json
{}
```

### Retorno da API

#### Sucesso

Retorna um json com todas as informações de cada uma das empresas existentes no sistema e informações do plano associado a elas

**Ex**:

```json
{
  "Companies": [
    {
      "id": 1,
      "plan_id": 1,
      "name": "Empresa 1",
      "corporate_name": "teste",
      "cnpj_cpf": "543345343543",
      "price": "222",
      "recurrency": 12,
      "discount": null,
      "active": true,
      "created": "2023-06-26T18:22:08-03:00",
      "modified": "2023-08-23T18:37:18-03:00",
      "deleted": null,
      "is_users": true,
      "is_forms": true,
      "is_files": true,
      "cusers": null,
      "cep": "343524323",
      "street": "teste",
      "number": "23",
      "district": "teste",
      "city": "teste",
      "state": "teste",
      "corporate_name": "teste",
      "financial_responsible_name": "teste",
      "financial_responsible_cpf_cnpj": "334325346",
      "financial_responsible_telephone": "546345243",
      "financial_responsible_cep": "3543643653",
      "financial_responsible_street": "teste",
      "financial_responsible_number": "243",
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
      "user_by_ajax": true,
      "action": true,
      "schedule": true,
      "meeting": true,
      "confirmed_meeting": true,
      "stock_update": true,
      "project_summary": true,
      "anomaly_registration": true,
      "schedule_training": true,
      "created_by": null,
      "deleted_by": null,
      "is_file_system": false,
      "work_on_saturday": false,
      "is_georeferencing": false,
      "is_gamefication": false,
      "plan": {
        "id": 1,
        "name": "Vitalício",
        "price_monthly": 0,
        "price_annual": 0,
        "price_trimesterly": 0,
        "price_semesterly": 0,
        "active": false,
        "created": null,
        "modified": null,
        "deleted": null,
        "created_by": null,
        "deleted_by": null
      }
    },
    {
      "id": 2,
      "plan_id": 2,
      "name": "Empresa 2",
      "corporate_name": "",
      "cnpj_cpf": "",
      "price": "",
      "recurrency": 12,
      "discount": null,
      "active": true,
      "created": "2023-04-28T09:09:02-03:00",
      "modified": "2023-05-02T07:09:50-03:00",
      "deleted": null,
      "is_users": true,
      "is_forms": true,
      "is_files": true,
      "cusers": null,
      "cep": "",
      "street": "",
      "number": "",
      "district": "",
      "city": "",
      "state": "",
      "financial_responsible_name": "",
      "financial_responsible_cpf_cnpj": "",
      "financial_responsible_telephone": "",
      "financial_responsible_cep": "",
      "financial_responsible_street": "",
      "financial_responsible_number": "",
      "financial_responsible_district": "",
      "financial_responsible_city": "",
      "financial_responsible_state": "",
      "is_actions": 1,
      "is_meets": 1,
      "is_checklists": 1,
      "is_calendars": 1,
      "is_anomalies": 1,
      "is_tickets": 1,
      "is_trainings": 1,
      "is_projects": 1,
      "is_events": 0,
      "tickets_is_in_sectors": true,
      "unit_by_ajax": false,
      "user_by_ajax": false,
      "action": false,
      "schedule": false,
      "meeting": false,
      "confirmed_meeting": false,
      "stock_update": false,
      "project_summary": false,
      "anomaly_registration": false,
      "schedule_training": false,
      "created_by": null,
      "deleted_by": null,
      "is_file_system": true,
      "work_on_saturday": true,
      "is_georeferencing": false,
      "is_gamefication": false,
      "plan": {
        "id": 2,
        "name": "Básico",
        "price_monthly": 400,
        "price_annual": 4000,
        "price_trimesterly": null,
        "price_semesterly": null,
        "active": null,
        "created": null,
        "modified": null,
        "deleted": null,
        "created_by": null,
        "deleted_by": null
      }
    }
  ],
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário não tiver nível de permissão igual a Master

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Você não tem permissão para acessar este recurso."
    }
    ```
