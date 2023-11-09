## Add

### Requisição para API

### 1. Adicionar nova função

#### Rota da API

POST -> `api/jobs`

#### Parâmetros e Suas Utilidades

Sem parâmetros

#### Exemplo de Requisição

POST -> `api/jobs`

Body:

```json
{
  "nome": "Exemplo 1"
}
```

### Retorno da API

#### Sucesso

Retorna um json contendo as informações da função que foi criada e uma mensagem de sucesso.

**Ex**:

```json
{
  "App\\Model\\Entity\\Job": {
    "name": "Exemplo 1",
    "company_id": 1,
    "created": "2023-11-09T01:36:42-03:00",
    "modified": "2023-11-09T01:36:42-03:00",
    "created_by": 3,
    "id": 1
  },
  "message": "Sucesso ao adicionar Função!",
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

2. Se acontecer algum erro ao tentar salvar a função será retornada a mensagem de erro

**Ex**:

```json
{
  "status": 0,
  "message": "Erro ao adicionar Função."
}
```
