## Gamefication History -> Best Users

### 1. Listagem dos melhores usuários de uma rodada

### Requisição para API

#### 1. Rota da API

GET-> `api/gamefication-history/best-users`
GET-> `api/gamefication-history/best-users/{Round_id}`

#### 2. Parâmetros e Suas Utilidades

Round_id: id da rodada que se deseja ver os melhores usuários(se não for especifícado será retornado os melhores usuários da rodada atual)

#### 3. Exemplo de Requisição

GET -> `api/gamefication-history/best-users`

Body:

```json
{}
```

### Retorno da API

#### Sucesso

Retorna um json com as informações de pontuação dos usuários ordenado por aqeueles que fizeram mais pontos na rodada específicada(ou na rodada atual) e o número da rodada que indica qual o número da rodada em relação a todas as rodadas da empresa.

**Ex**:

```json
{
  "bestUsers": [
    {
      "user_id": 1,
      "total_points": "75",
      "user_name": "Usuário 1"
    },
    {
      "user_id": 2,
      "total_points": "7",
      "user_name": "Usuário 2"
    },
    {
      "user_id": 3,
      "total_points": "4",
      "user_name": "Usuário 3"
    },
    {
      "user_id": 4,
      "total_points": "4",
      "user_name": "Usuário 4"
    },
    {
      "user_id": 5,
      "total_points": "4",
      "user_name": "Usuário 5"
    },
    {
      "user_id": 6,
      "total_points": "2",
      "user_name": "Usuário 6"
    }
  ],
  "num_of_round": 3,
  "status": 1
}
```

#### Erro(s)

Não possui erros possíveis
