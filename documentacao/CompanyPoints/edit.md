## Company Points -> Edit

### 1. Editar uma atividade ativa

### Requisição para API

#### 1. Rota da API

PUT -> `api/company-points/{Nome em português da atividade}`

#### 2. Parâmetros e Suas Utilidades

Nome em português da atividade\*: o nome em português da atividade que será editada

#### 3. Exemplo de Requisição

PUT -> `api/company-points/Completar%20Rotina%20Produtiva`

Body:

```json
{
  "value": 40,
  "max": 10
}
```

### Retorno da API

#### Sucesso

Retorna um json contendo as informações de todas as pontuações atuais das atividades e uma mensagem de sucesso. A atividade que foi passada como parâmetro terá os pontos que ela gera e o máximo de vezes que ela gera pontos por dia salvas no sistema. Se os pontos que ela gera ou o máximo de vezes que ela gera pontos for 0 a atividade não vai gerar pontos ou ter suas informações detalhadas retornadas no index.

**Ex**:

```json
{
  "App\\Model\\Entity\\CompanyPoint": {
    "id": 3,
    "company_id": 1,
    "add_action": 1,
    "complete_ongoing_action": 5,
    "complete_delayed_action": 3,
    "create_meet": 1,
    "is_present_on_meet": 3,
    "create_project": 1,
    "create_event": 2,
    "create_anomaly": 1,
    "create_form": 1,
    "complete_form": 2,
    "create_checklist": 1,
    "complete_checklist": 2,
    "create_ticket": 1,
    "complete_ticket_without_solution": 3,
    "complete_ticket": 7,
    "create_training": 1,
    "make_schedule_training": 1,
    "is_present_on_training": 4,
    "create_class_video_training": 5,
    "half_calendar": 1,
    "complete_calendar": 40,
    "max_add_action": 5,
    "max_complete_ongoing_action": 5,
    "max_complete_delayed_action": 5,
    "max_create_meet": 5,
    "max_is_present_on_meet": 5,
    "max_create_project": 5,
    "max_create_event": 5,
    "max_create_anomaly": 5,
    "max_create_form": 5,
    "max_complete_form": 5,
    "max_create_checklist": 5,
    "max_complete_checklist": 5,
    "max_create_ticket": 5,
    "max_complete_ticket_without_solution": 5,
    "max_complete_ticket": 5,
    "max_create_training": 5,
    "max_make_schedule_training": 5,
    "max_is_present_on_training": 5,
    "max_create_class_video_training": 5,
    "max_half_calendar": 5,
    "max_complete_calendar": 10,
    "complete_training": 2,
    "max_complete_training": 0
  },
  "message": "A geração de pontos da atividade Completar Rotina Produtiva foi editada com sucesso.",
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário não for Master ou então não for Admin tentando editar a pontuação de uma atividade na empresa que participa

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Você não tem permissão para acessar este recurso!"
    }
    ```

2.  Se acontecer algum erro ao tentar salvar as informações da atividade passada como parâmetro

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "A geração de pontos da atividade {Nome da atividade} não pôde ser editada. Por favor, tente novamente."
    }
    ```
