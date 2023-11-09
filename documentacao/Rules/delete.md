## Rules -> Delete

### 1. Deletar uma regra

### Requisição para API

#### 1. Rota da API

DELETE -> `api/rules/{Rule_id}`

#### 2. Parâmetros e Suas Utilidades

Rule_id\*: o id da regra que será deletada

#### 3. Exemplo de Requisição

DELETE -> `api/rules/1`

Body:

```json
{}
```

### Retorno da API

#### Sucesso

Retorna um json contendo as informações da regra que foi deletada e uma mensagem de sucesso.

**Ex**:

```json
{
  "App\\Model\\Entity\\Rule": {
    "id": 1,
    "name": "Exemplo 1",
    "company_id": 1,
    "created": "2023-11-09T01:36:42-03:00",
    "modified": "2023-11-09T01:43:11-03:00",
    "active": true,
    "deleted": null,
    "created_by": 3,
    "deleted_by": 3
  },
  "message": "Sucesso ao deletar Regra!",
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando deletar uma regra da empresa que participa

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Você não tem permissão para acessar esse recurso!"
    }
    ```

2.  Se a regra passada como parâmetro não for encontrada

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Registro não encontrado!"
    }
    ```

3.  Se acontecer algum erro ao tentar deletar a regra passada como parâmetro

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Erro ao deletar Regra!"
    }
    ```

4.  Se acontecer algum outro erro ao tentar achar a regra passada como parâmetro

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Erro interno no sistema"
    }
    ```
