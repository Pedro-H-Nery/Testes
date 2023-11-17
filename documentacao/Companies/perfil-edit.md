## Companies -> Perfil Edit

### 1. Editar o perfil de uma empresa

### Requisição para API

#### 1. Rota da API

POST -> `api/companies/perfil-edit/{Company_id}`

#### 2. Parâmetros e Suas Utilidades

Company_id\*: o id da empresa que se deseja editar as informações de perfil

#### 3. Exemplo de Requisição

POST -> `api/companies/perfil-edit//1`

Body:

```json
{
  "name": "Empresa 1 Alterada",
  "corporate_name": "teste",
  "cnpj_cpf": "36634532",
  "street": "teste",
  "cep": "1111111",
  "number": "664",
  "district": "teste",
  "city": "teste",
  "state": "teste",
  "financial_responsible_name": "teste",
  "financial_responsible_cpf_cnpj": "",
  "financial_responsible_telephone": "54635523",
  "financial_responsible_cep": "55555555",
  "financial_responsible_street": "teste",
  "financial_responsible_number": "222",
  "financial_responsible_district": "teste",
  "financial_responsible_city": "teste",
  "financial_responsible_state": "teste",
  "plan": [],
  "recurrency": "12",
  "price": "0",
  "discount": "100",
  "action": "1",
  "schedule": "1",
  "meeting": "1",
  "confirmed_meeting": "1",
  "stock_update": "1",
  "project_summary": "0",
  "anomaly_registration": "1",
  "schedule_training": "1",
  "is_events": "1",
  "is_meets": "1",
  "is_actions": "1",
  "is_projects": "1",
  "is_anomalies": "1",
  "is_checklists": "1",
  "is_forms": "1",
  "is_calendars": "1",
  "is_tickets": "1",
  "is_trainings": "1",
  "is_files": "1",
  "is_users": "1",
  "tickets_is_in_sectors": "1",
  "is_file_system": "1",
  "work_on_saturday": "0",
  "is_georeferencing": "1",
  "is_gamefication": "1"
}
```

OBS: o atributo `is_gamefication` é obrigatório e os outros são opcionais. Se o usuário tiver selecionado `Possui Gameficação` em uma empresa em que essa opção não estava ativda então será criado um registro da pontuação das atividades da empresa e duas rodadas(a rodada atual e a próxima rodada) e elas poderão ser modificação no Módulo de Gameficação. Se o opção `Possui Gameficação` já estava selecionada e o usuário desativou ela então o registro de pontuação das atividades da empresa será deletado.

### Retorno da API

#### Sucesso

Retorna um json com as informações da empresa que teve seu perfil alterado com as informações do plano dela e uma mensagem de sucesso.

**Ex**:

```json
{
  "App\\Model\\Entity\\Company": {
    "id": 1,
    "plan_id": 1,
    "name": "Empresa 1 Alterada",
    "corporate_name": "teste",
    "cnpj_cpf": "36634532",
    "price": "0",
    "recurrency": 12,
    "discount": 100,
    "active": true,
    "created": null,
    "modified": "2023-11-17T12:40:10-03:00",
    "deleted": null,
    "is_users": true,
    "is_forms": true,
    "is_files": true,
    "cusers": true,
    "cep": "1111111",
    "street": "teste",
    "number": "664",
    "district": "teste",
    "city": "teste",
    "state": "teste",
    "financial_responsible_name": "teste",
    "financial_responsible_cpf_cnpj": "",
    "financial_responsible_telephone": "54635523",
    "financial_responsible_cep": "55555555",
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
  "message": "Compania atualizada com sucesso!",
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

2.  Se acontecer algum erro ao tentar editar o perfil da empresa

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Erro ao atualizar compania!"
    }
    ```
