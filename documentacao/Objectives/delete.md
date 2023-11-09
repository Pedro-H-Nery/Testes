## Objectives -> Delete

### 1. Deletar um objetivo

### Requisição para API

#### 1. Rota da API

DELETE -> `api/objectives/{Objective_id}`

#### 2. Parâmetros e Suas Utilidades

Objective_id\*: o id do objetivo que será deletado

#### 3. Exemplo de Requisição

DELETE -> `api/objectives/1`

Body:

```json
{}
```

### Retorno da API

#### Sucesso

Retorna um json contendo as informações do objetivo que foi deletado e uma mensagem de sucesso.

**Ex**:

```json
{
  "App\\Model\\Entity\\Objective": {
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
  "message": "Sucesso ao deletar Objetivo!",
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando deletar um objetivo da empresa que participa

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Você não tem permissão para acessar esse recurso!"
    }
    ```

2.  Se o objetivo passado como parâmetro não for encontrado

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Registro não encontrado!"
    }
    ```

3.  Se acontecer algum erro ao tentar deletar o objetivo passado como parâmetro

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Erro ao deletar Objetivo!"
    }
    ```

4.  Se acontecer algum outro erro ao tentar achar o objetivo passado como parâmetro

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Erro interno no sistema"
    }
    ```
