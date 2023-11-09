## Rulings -> Delete

### 1. Deletar uma pauta

### Requisição para API

#### 1. Rota da API

DELETE -> `api/rulings/{Ruling_id}`

#### 2. Parâmetros e Suas Utilidades

Ruling_id\*: o id da pauta que será deletada

#### 3. Exemplo de Requisição

DELETE -> `api/rulings/1`

Body:

```json
{}
```

### Retorno da API

#### Sucesso

Retorna um json contendo as informações da pauta que foi deletada e uma mensagem de sucesso.

**Ex**:

```json
{
  "App\\Model\\Entity\\Ruling": {
    "id": 1,
    "company_id": 1,
    "name": "Exemplo 1",
    "active": null,
    "deleted": null,
    "created": "2023-11-09T12:20:15-03:00",
    "modified": "2023-11-09T12:27:04-03:00",
    "created_by": 3,
    "deleted_by": 3
  },
  "message": "Sucesso ao deletar Pauta!",
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando deletar uma pauta da empresa que participa

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Você não tem permissão para acessar esse recurso!"
    }
    ```

2.  Se a pauta passada como parâmetro não for encontrada

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Registro não encontrado!"
    }
    ```

3.  Se acontecer algum erro ao tentar deletar a pauta passada como parâmetro

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Erro ao deletar Pauta!"
    }
    ```

4.  Se acontecer algum outro erro ao tentar achar a pauta passada como parâmetro

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Erro interno no sistema"
    }
    ```
