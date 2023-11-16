## Company Points -> Index

### 1. Listagem de todas as atividades ativas

### Requisição para API

#### 1. Rota da API

GET-> `api/company-points`

#### 2. Parâmetros e Suas Utilidades

Sem parâmetros

#### 3. Exemplo de Requisição

GET -> `api/company-points`

Body:

```json
{}
```

### Retorno da API

#### Sucesso

Retorna um json contendo todas as atividades da empresa que geram pontos e dentro de cada atividade está os pontos que ela gera ao ser feita e o máximo de vezes que ela gera pontos por dia. Se uma atividade tiver pontos iguais a 0 ou então seu máximo de vezes que pode ser concluída for 0 ou então for deletada então as informações detalhadas dela não vão ser retornadas

**Ex**:

```json
{
  "CompanyPoints": {
    "id": 3,
    "company_id": 1,
    "add_action": 0,
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
    "max_add_action": 0,
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
    "max_complete_calendar": 0,
    "complete_training": 2,
    "max_complete_training": 0,
    "activities": {
      "Concluir Ação em Andamento": {
        "points": 5,
        "max": 5
      },
      "Concluir Ação Atrasada": {
        "points": 3,
        "max": 5
      },
      "Criar Reunião": {
        "points": 1,
        "max": 5
      },
      "Estar presente em uma Reunião": {
        "points": 3,
        "max": 5
      },
      "Criar Projeto": {
        "points": 1,
        "max": 5
      },
      "Criar Compromisso": {
        "points": 2,
        "max": 5
      },
      "Criar Problema": {
        "points": 1,
        "max": 5
      },
      "Criar Formulário": {
        "points": 1,
        "max": 5
      },
      "Concluir Formulário": {
        "points": 2,
        "max": 5
      },
      "Criar Checklist": {
        "points": 1,
        "max": 5
      },
      "Concluir Checklist": {
        "points": 2,
        "max": 5
      },
      "Criar Chamado": {
        "points": 1,
        "max": 5
      },
      "Concluir Chamado sem Solução": {
        "points": 3,
        "max": 5
      },
      "Resolver Chamado": {
        "points": 7,
        "max": 5
      },
      "Criar uma Formação": {
        "points": 1,
        "max": 5
      },
      "Fazer um Agendamento": {
        "points": 1,
        "max": 5
      },
      "Estar presente em uma Formação": {
        "points": 4,
        "max": 5
      },
      "Criar Formação Por Vídeo Aula": {
        "points": 5,
        "max": 5
      },
      "Fazer Metade da Rotina Produtiva": {
        "points": 1,
        "max": 5
      }
    }
  },
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário não for Master ou então não for Admin tentando ver os Company Points da empresa que participa

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Você não tem permissão para acessar este recurso."
    }
    ```
