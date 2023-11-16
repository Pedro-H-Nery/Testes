## Company Points -> Add

### 1. Adicionar nova atividade ativa

### Requisição para API

#### 1. Rota da API

POST -> `api/company-points`

#### 2. Parâmetros e Suas Utilidades

Sem parâmetros

#### 3. Exemplo de Requisição

POST -> `api/company-points`

Body:

```json
{
  "activities": ["add_action", "complete_calendar"]
}
```

### Retorno da API

#### Sucesso

Retorna um json contendo as informações de todas as pontuações atuais das atividades e uma mensagem de sucesso. As atividades que foram escolhidas para serem adicionadas pelo usuário são salvas no sistema com seus valores de pontuação padrão e vão começar a gerar pontos

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
    "complete_calendar": 3,
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
    "max_complete_calendar": 5,
    "complete_training": 2,
    "max_complete_training": 0
  },
  "message": "As atividades tiveram suas pontuações padrões atribuidas com sucesso.",
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário não for Master ou então não for Admin tentando adicionar pontuação em uma atividade na empresa que participa

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Você não tem permissão para acessar este recurso."
    }
    ```

2.  Se acontecer algum erro ao tentar salvar a função será retornada a mensagem de erro

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Não foi possível atribuir pontuação as atividades. Por favor, tente novamente."
    }
    ```

3.  Se todas as atividades disponíveis já estão ativas

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Não existem mais atividades para atribuir uma pontuação."
    }
    ```
