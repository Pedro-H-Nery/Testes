## Rules -> Add

### 1. Adicionar nova regra

### Requisição para API

#### 1. Rota da API

POST -> `api/rules`

#### 2. Parâmetros e Suas Utilidades

Sem parâmetros

#### 3. Exemplo de Requisição

POST -> `api/rules`

Body:

```json
{
  "nome": "Exemplo 1"
}
```

### Retorno da API

#### Sucesso

Retorna um json contendo as informações da regra que foi criada e uma mensagem de sucesso.

**Ex**:

```json
{
  "App\\Model\\Entity\\Rule": {
    "name": "Exemplo 1",
    "company_id": 1,
    "created": "2023-11-09T01:36:42-03:00",
    "modified": "2023-11-09T01:36:42-03:00",
    "created_by": 3,
    "id": 1
  },
  "message": "Sucesso ao adicionar Regra!",
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário não tiver um nível de permissão igual ou superior a Gestor

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Você não tem permissão para acessar este recurso."
    }
    ```

2.  Se acontecer algum erro ao tentar salvar a regra

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Erro ao adicionar Regra."
    }
    ```
