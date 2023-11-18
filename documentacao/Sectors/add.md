## Sectors -> Add

### 1. Adicionar novo setor

### Requisição para API

#### 1. Rota da API

POST -> `api/sectors`

#### 2. Parâmetros e Suas Utilidades

Sem parâmetros

#### 3. Exemplo de Requisição

POST -> `api/sectors`

Body:

```json
{
  "nome": "Exemplo 1"
}
```

### Retorno da API

#### Sucesso

Retorna um json contendo as informações do setor que foi criado e uma mensagem de sucesso.

**Ex**:

```json
{
  "App\\Model\\Entity\\Sector": {
    "name": "Exemplo 1",
    "company_id": 1,
    "created": "2023-11-09T11:10:17-03:00",
    "modified": "2023-11-09T11:10:17-03:00",
    "created_by": 3,
    "id": 1
  },
  "message": "Sucesso ao adicionar Setor!",
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

2.  Se acontecer algum erro ao tentar salvar o setor

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Erro ao adicionar Setor."
    }
    ```
