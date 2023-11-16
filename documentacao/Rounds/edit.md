## Rounds -> Edit

### 1. Editar uma rodada

### Requisição para API

#### 1. Rota da API

PUT -> `api/rounds/{Round_id}`

#### 2. Parâmetros e Suas Utilidades

Round_id\*: id da rodada que será editada

#### 3. Exemplo de Requisição

PUT -> `api/rounds/1`

Body:

```json
{
  "month": 3,
  "type": 3
}
```

### Retorno da API

#### Sucesso

Retorna um json com as informações da rodada editada pelo usuário e uma mensagem de sucesso. Se a próxima rodada não for a que foi passada como parâmetro e ainda não teve suas informações definifas ela terá suas informações alteradas baseada na rodada salva.

**Ex**:

```json
{
  "App\\Model\\Entity\\Round": {
    "id": 5,
    "company_id": 1,
    "init": "2024-06-01T00:00:00-03:00",
    "end": "2024-11-30T00:00:00-03:00",
    "type": 3
  },
  "message": "Sucesso ao editar Rodada.",
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário não for Master ou então não for Admin tentando editar uma rodadas da empresa que participa

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Você não tem permissão para acessar este recurso."
    }
    ```

2.  Se acontecer algum erro ao tentar salvar as informações da rodada passada como parâmetro

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Erro ao editar Rodada."
    }
    ```

3.  Se já existir um conflito de datas entre a rodada editada pelo usuário e alguma rodada ativa e/ou cadastrada

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Já existe uma rodada cadastrada nessa data."
    }
    ```
