## Rounds -> Index

### 1. Listagem de todas as rodadas

### Requisição para API

#### 1. Rota da API

GET-> `api/rounds`

#### 2. Parâmetros e Suas Utilidades

Sem parâmetros

#### 3. Exemplo de Requisição

GET -> `api/rounds`

Body:

```json
{}
```

### Retorno da API

#### Sucesso

Retorna um json com as informações de todas as rodadas passadas, da rodada atual e da próxima rodada da empresa

**Ex**:

```json
{
  "Rounds": [
    {
      "id": 4,
      "company_id": 1,
      "init": "2023-10-01",
      "end": "2024-03-31",
      "type": 3
    },
    {
      "id": 3,
      "company_id": 1,
      "init": "2023-09-01",
      "end": "2023-09-30",
      "type": 1
    },
    {
      "id": 2,
      "company_id": 1,
      "init": "2023-08-01",
      "end": "2023-08-31",
      "type": 1
    }
  ],
  "NextRound": {
    "id": 5,
    "company_id": 1,
    "init": "2024-07-01",
    "end": "2024-08-31",
    "type": 2
  },
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário não for Master ou então não for Admin tentando ver as Rodadas da empresa que participa

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Você não tem permissão para acessar este recurso."
    }
    ```
