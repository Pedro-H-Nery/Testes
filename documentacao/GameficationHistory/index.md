## Gamefication History -> Index

### 1. Listagem do histórico de pontos de um usuário

### Requisição para API

#### 1. Rota da API

GET -> `api/gamefication-history`

GET -> `api/gamefication-history/{User_id}`

#### 2. Parâmetros e Suas Utilidades

User_id: id do usuário que se deseja ver o histórico(se não for especifícado será retornado o histórico do usuário atual)

#### 3. Exemplo de Requisição

GET -> `api/gamefication-history/10`

Body:

```json
{}
```

### Retorno da API

#### Sucesso

Retorna um json com as informações de cada uma das atividades feitas pelo usuário, o seu total de pontos e uma messagem de titulo para indicar os pontos do usuário(Se o usuário estiver tentando ver o próprio histórico a mensagem será: `Seus Pontos na Rodada Atual: {Pontos}` e se tiver vendo o histórico de outro usuário será: `Pontos de Usuário 1 na Rodada Atual: {Pontos}`)

**Ex**:

```json
{
  "GameficationHistory": [
    {
      "id": 40,
      "company_id": 1,
      "user_id": 10,
      "activity": "is_present_on_training",
      "model": "TestSchedules",
      "model_id": 44,
      "date": "2023-10-08T20:47:48-03:00",
      "points": 4,
      "round_id": 4,
      "name": "Formação X",
      "num_of_round": "Rodada 3",
      "activity_name": "Estar presente em uma Formação"
    },
    {
      "id": 46,
      "company_id": 1,
      "user_id": 10,
      "activity": "complete_training",
      "model": "TestSchedules",
      "model_id": 45,
      "date": "2023-10-08T20:51:10-03:00",
      "points": 2,
      "round_id": 4,
      "name": "Treinamento Y",
      "num_of_round": "Rodada 3",
      "activity_name": "Completar Treinamento"
    },
    {
      "id": 47,
      "company_id": 1,
      "user_id": 10,
      "activity": "create_anomaly",
      "model": "Anomalies",
      "model_id": 135,
      "date": "2023-10-08T21:00:46-03:00",
      "points": 1,
      "round_id": 4,
      "name": "Problema Z",
      "num_of_round": "Rodada 3",
      "activity_name": "Criar Problema"
    }
  ],
  "userPoints": 7,
  "messagePoints": "Pontos de Usuário 1 na Rodada Atual: 7",
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário não estiver tentando ver o próprio histórico ou não for um usuário de nível de permissão igual ou superior a Gestor tentando ver o histórico de um usuário

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Você não tem permissão para acessar este recurso."
    }
    ```
