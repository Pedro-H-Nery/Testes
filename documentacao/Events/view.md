## Events -> View

### 1. Visualizar um Evento da Agenda

### Requisição para API

#### 1. Rota da API

GET -> `api/events/{User_id}/{Model_type}/{Model_id}?start={Data}&share_code={Código}&redirect={Link}`

#### 2. Parâmetros e Suas Utilidades

User_id\*: id do usuário que está tentando ver um evento da agenda.

Model_type\*: modelo do evento que o usuário está tentando ver. Pode ser: `event` para compromissos, `action` para ações, `holiday` para ausências, `ticket` para chamados, `training` para formações, `schedule` para reuniões e `task` para tarefas da rotina produtiva.

Model_id\*: id do modelo do evento que o usuário está tentando ver.

start: Data em que o evento começou. Obrigatório caso o Model_type seja `task`.

share_code: Código de compartilhamento da agenda. Obrigatório caso o usuário esteja tentando ver o evento de outro usuário.

redirect: Link de redirecionamento usado quando o usuário interage com o evento que está visualizando. Obrigatório quando o Model_type for `action`, `holiday` e `ticket`,

#### 3. Exemplo de Requisição

GET -> `api/events/2/action/1?start=2023-06-29&share_code=v6465cw34334564v5vqc34&redirect={Início da url}/events?company_id=1&unit_id=1`

`Exemplo de Início da url: http://localhost/pastaDoProjeto`

Body:

```json
{}
```

### Retorno da API

#### Sucesso

Retorna um json contendo as informações do evento espeficicado pelo Model_type e pelo Model_id. Se o model id for:
`event` -> Informações do compromisso incluindo informações da empresa, usuário dono do compromisso e dos usuário que são convidados do compromisso;
`action` -> Informações da ação incluindo informações da empresa, dos usuários responsáveis pela ação e do usuário dono da ação;
`holiday` -> Informações da ausência incluindo informações das unidades em que a ausência é válida e do usuário que é afetado pela ausência(mesmo que a ausência seja apenas para unidade(s) ou para um usuário);
`ticket` -> Informações do chamado incluindo informações da empresa, da unidade responsável pelo chamado, do usuário que fez o último comentário no chamado, do usuário dono do chamado, do setor responsável pelo chamado e das unidades responsáveis pelo chamado(mesmo que o chamado seja apenas para um setor ou para uma unidade);
`training` -> Informações da formação incluindo informações da unidade que está a formação;
`schedule` -> Informaçoes da reunião incluindo informações da unidade que está a reunião, do usuário dono da reunião, da frequência da reunião, dos usuários participantes e dos usuários convidados da reunião;
`task` -> Informações da tarefa da rotina produtiva incluindo informações da unidade que está a rotina produtiva.

**Ex**:

```json
{
  "action": {
    "id": 1,
    "user_id": 2,
    "schedule_id": null,
    "meet_id": null,
    "sector_id": null,
    "indicator_id": null,
    "managerment_tool_id": null,
    "company_id": 1,
    "anomaly_id": null,
    "project_id": 1,
    "status": 3,
    "due_date": "2023-08-03",
    "action": "Ação 1",
    "active": true,
    "end": null,
    "created": "2023-06-29T15:13:24-03:00",
    "modified": "2023-06-29T15:13:57-03:00",
    "done_date": "2023-06-29",
    "rating": 0,
    "deleted": null,
    "created_by": 2,
    "deleted_by": null,
    "user": {
      "id": 2,
      "unit_id": 1,
      "sector_id": 2,
      "job_id": 2,
      "name": "Usuário 2",
      "email": "usuario2@gmail.com",
      "phone": "(88)88888-8888",
      "admission": "2000-12-01",
      "photo_url": "usuario2.png",
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
      "calendar_share_code": "cn6y46t66omywxrr6x6gc6",
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
    "responsibles": [
      {
        "user_id": 2,
        "action_id": 1,
        "user": {
          "id": 2,
          "unit_id": 1,
          "sector_id": 2,
          "job_id": 2,
          "name": "Usuário 2",
          "email": "usuario2@gmail.com",
          "phone": "(88)88888-8888",
          "admission": "2000-12-01",
          "photo_url": "usuario2.png",
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
          "calendar_share_code": "cn6y46t66omywxrr6x6gc6",
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
    ],
    "company": {
      "id": 1,
      "plan_id": 1,
      "name": "Empresa 1",
      "corporate_name": "Empresa 1 LTDA",
      "cnpj_cpf": "456354523434",
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
      "cep": "33333-333",
      "street": "teste",
      "number": "222",
      "district": "teste",
      "city": "teste",
      "state": "teste",
      "financial_responsible_name": "teste",
      "financial_responsible_cpf_cnpj": "",
      "financial_responsible_telephone": "(88) 8 888-8888",
      "financial_responsible_cep": "33333333",
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
  "redirect": null,
  "user": {
    "id": 2,
    "unit_id": 1,
    "sector_id": 2,
    "job_id": 2,
    "name": "Usuário 2",
    "email": "usuario2@gmail.com",
    "phone": "(88)88888-8888",
    "admission": "2000-12-01",
    "photo_url": "usuario2.png",
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
    "calendar_share_code": "cn6y46t66omywxrr6x6gc6",
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
    "deleted_by": null,
    "share_code": null
  },
  "model_type": "action",
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário não for Master ou então não for um usuário de nível de permissão igual a Admin tentando ver um evento não privado de um usuário de nível de permissão menor da empresa que participa ou então não for um usuário de nível de permissão igual a Gestor tentando ver um evento não privado de um usuário de nível de permissão menor na empresa que participa ou então não for o dono/responsável pelo evento ou então não possui o código de compartilhamento correspondente ao dono/responsável pelo evento da empresa em que participa

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Você não tem permissão para acessar este recurso."
    }
    ```

OBS: Possui os erros associados ao modelo que o usuário está tentando ver, ou seja, se o usuário está tentando ver uma reunião então os erros que acontecem ao tentar ver uma reunião também se aplicam ao tentar ver uma reunião na agenda.
