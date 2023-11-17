## Companies -> Perfil Company

### 1. Ver o perfil da empresa

### Requisição para API

#### 1. Rota da API

GET -> `api/companies/perfil-company/{Company_id}`

#### 2. Parâmetros e Suas Utilidades

Company_id\*: o id da empresa que se deseja ver o perfil

#### 3. Exemplo de Requisição

GET -> `api/companies/perfil-company/1`

Body:

```json
{}
```

### Retorno da API

#### Sucesso

Retorna um json com as informações da empresa que foi passada com parâmetro e também o nome dos planos disponíveis.

**Ex**:

```json
{
  "Company": {
    "id": 1,
    "plan_id": 1,
    "name": "Empresa 1",
    "corporate_name": "teste",
    "cnpj_cpf": "4334366",
    "price": "0",
    "recurrency": 12,
    "discount": 100,
    "active": true,
    "created": null,
    "modified": "2023-10-04T17:54:47-03:00",
    "deleted": null,
    "is_users": true,
    "is_forms": true,
    "is_files": true,
    "cusers": true,
    "cep": "35363423",
    "street": "teste",
    "number": "432",
    "district": "teste",
    "city": "teste",
    "state": "teste",
    "financial_responsible_name": "teste",
    "financial_responsible_cpf_cnpj": "",
    "financial_responsible_telephone": "5346333423",
    "financial_responsible_cep": "3463452",
    "financial_responsible_street": "teste",
    "financial_responsible_number": "355",
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
    "project_summary": true,
    "anomaly_registration": true,
    "schedule_training": true,
    "created_by": null,
    "deleted_by": null,
    "is_file_system": true,
    "work_on_saturday": false,
    "is_georeferencing": true,
    "is_gamefication": true,
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
  "Plans": {
    "1": "Vitalício",
    "2": "Básico"
  },
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
