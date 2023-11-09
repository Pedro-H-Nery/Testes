## Units -> Add

### 1. Adicionar nova unidade

### Requisição para API

#### 1. Rota da API

POST -> `api/units`

#### 2. Parâmetros e Suas Utilidades

Sem parâmetros

#### 3. Exemplo de Requisição

POST -> `api/units`

Body:

```json
{
  "name": "Exemplo 1",
  "acronym": "[EX1]",
  "latitude": "-5.079222",
  "longitude": "-42.761417"
}
```

OBS: os atributos `acronym`, `latitude` e `longitude` são opcionais

### Retorno da API

#### Sucesso

Retorna um json contendo as informações da unidade que foi criada e uma mensagem de sucesso.

**Ex**:

```json
{
  "App\\Model\\Entity\\Unit": {
    "name": "Exemplo 1",
    "acronym": "[EX1]",
    "latitude": "-5.079222",
    "longitude": "-42.761417",
    "company_id": 1,
    "created": "2023-11-09T12:41:30-03:00",
    "modified": "2023-11-09T12:41:30-03:00",
    "created_by": 3,
    "id": 1
  },
  "message": "Sucesso ao adicionar Unidade!",
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário não tiver um nível de permissão igual ou superior Gestor será retornada a mensagem de erro

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Você não tem permissão para acessar este recurso."
    }
    ```

2.  Se acontecer algum erro ao tentar salvar a unidade será retornada a mensagem de erro

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Erro ao adicionar Unidade."
    }
    ```
