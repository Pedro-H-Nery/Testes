## Managerment Tools -> Edit

### 1. Editar uma ferramenta de gestão

### Requisição para API

#### 1. Rota da API

PUT -> `api/managerment_tools/{ManagermentTool_id}`

#### 2. Parâmetros e Suas Utilidades

ManagermentTool_id\*: o id da ferramenta de gestão que será editada

#### 3. Exemplo de Requisição

PUT -> `api/managerment_tools/1`

Body:

```json
{
  "nome": "Exemplo 1 Alterado"
}
```

### Retorno da API

#### Sucesso

Retorna um json contendo as informações da ferramenta de gestão que foi editada e uma mensagem de sucesso.

**Ex**:

```json
{
  "App\\Model\\Entity\\ManagermentTool": {
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
  "message": "Sucesso ao editar Ferramenta de Gestão!",
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando editar uma ferramenta de gestão da empresa que participa

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Você não tem permissão para acessar esse recurso!"
    }
    ```

2.  Se a ferramenta de gestão passada como parâmetro não for encontrada

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Registro não encontrado!"
    }
    ```

3.  Se acontecer algum erro ao tentar salvar a ferramenta de gestão passada como parâmetro

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Erro ao editar Ferramenta de Gestão!"
    }
    ```

4.  Se acontecer algum outro erro ao tentar achar a ferramenta de gestão passada como parâmetro

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Erro interno no sistema"
    }
    ```
