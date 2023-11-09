## Objectives -> Edit

### 1. Editar um objetivo

### Requisição para API

#### 1. Rota da API

PUT -> `api/objectives/{Objective_id}`

#### 2. Parâmetros e Suas Utilidades

Objective_id\*: o id do objetivo que será editado

#### 3. Exemplo de Requisição

PUT -> `api/objectives/1`

Body:

```json
{
  "nome": "Exemplo 1 Alterado"
}
```

### Retorno da API

#### Sucesso

Retorna um json contendo as informações do objetivo que foi editado e uma mensagem de sucesso.

**Ex**:

```json
{
  "App\\Model\\Entity\\Objective": {
    "id": 1,
    "name": "Exemplo 1 Alterado",
    "company_id": 1,
    "created": "2023-11-09T01:47:29-03:00",
    "modified": "2023-11-09T01:47:39-03:00",
    "active": true,
    "deleted": null,
    "created_by": 3,
    "deleted_by": null
  },
  "message": "Sucesso ao editar Objetivo!",
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando editar um objetivo da empresa que participa

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

3.  Se acontecer algum erro ao tentar salvar o objetivo passado como parâmetro

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Erro ao editar Objetivo!"
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
