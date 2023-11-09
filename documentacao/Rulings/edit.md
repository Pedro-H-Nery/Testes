## Rulings -> Edit

### 1. Editar uma pauta

### Requisição para API

#### 1. Rota da API

PUT -> `api/rulings/{Ruling_id}`

#### 2. Parâmetros e Suas Utilidades

Ruling_id\*: o id da pauta que será editada

#### 3. Exemplo de Requisição

PUT -> `api/rulings/1`

Body:

```json
{
  "nome": "Exemplo 1 Alterado"
}
```

### Retorno da API

#### Sucesso

Retorna um json contendo as informações da pauta que foi editada e uma mensagem de sucesso.

**Ex**:

```json
{
  "App\\Model\\Entity\\Ruling": {
    "id": 1,
    "company_id": 1,
    "name": "Exemplo 1 Alterado",
    "active": null,
    "deleted": null,
    "created": "2023-11-09T12:20:15-03:00",
    "modified": "2023-11-09T12:23:19-03:00",
    "created_by": 3,
    "deleted_by": null
  },
  "message": "Sucesso ao editar Pauta!",
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando editar uma pauta da empresa que participa

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

3.  Se acontecer algum erro ao tentar salvar a pauta passada como parâmetro

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Erro ao editar Pauta!"
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
