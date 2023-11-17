## Companies -> Delete

### 1. Deletar uma empresa

### Requisição para API

#### 1. Rota da API

DELETE -> `api/companies/{Company_id}`

#### 2. Parâmetros e Suas Utilidades

Company_id\*: o id da empresa que se deseja deletar

#### 3. Exemplo de Requisição

DELETE -> `api/companies/1`

Body:

```json
{}
```

### Retorno da API

#### Sucesso

Retorna um json com as informações da empresa que foi deletada e uma mensagem de sucesso.

**Ex**:

```json
{
  "App\\Model\\Entity\\Company": {
    "id": 1,
    "plan_id": 1,
    "name": "Empresa 1",
    "corporate_name": "teste",
    "cnpj_cpf": "543345343543",
    "price": "222",
    "recurrency": 3,
    "discount": 40,
    "active": true,
    "created": "2023-11-17T12:04:25-03:00",
    "modified": "2023-11-17T12:24:19-03:00",
    "deleted": null,
    "is_users": null,
    "is_forms": null,
    "is_files": null,
    "cusers": null,
    "cep": "343524323",
    "street": "teste",
    "number": "23",
    "district": "teste",
    "city": "teste",
    "state": "teste",
    "financial_responsible_name": "teste",
    "financial_responsible_cpf_cnpj": "334325346",
    "financial_responsible_telephone": "546345243",
    "financial_responsible_cep": "3543643653",
    "financial_responsible_street": "teste",
    "financial_responsible_number": "243",
    "financial_responsible_district": "teste",
    "financial_responsible_city": "teste",
    "financial_responsible_state": "teste",
    "is_actions": 0,
    "is_meets": 0,
    "is_checklists": 0,
    "is_calendars": 0,
    "is_anomalies": 0,
    "is_tickets": 0,
    "is_trainings": 0,
    "is_projects": 0,
    "is_events": 0,
    "tickets_is_in_sectors": true,
    "unit_by_ajax": false,
    "user_by_ajax": false,
    "action": null,
    "schedule": null,
    "meeting": null,
    "confirmed_meeting": null,
    "stock_update": null,
    "project_summary": null,
    "anomaly_registration": null,
    "schedule_training": null,
    "created_by": 3,
    "deleted_by": 3,
    "is_file_system": true,
    "work_on_saturday": true,
    "is_georeferencing": false,
    "is_gamefication": false
  },
  "message": "A compania Empresa 1 foi deletada.",
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

2.  Se acontecer algum erro ao tentar deletar a empresa

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "A compania {Nome da empresa} não pode ser deletada. Por favor, tente novamente."
    }
    ```
