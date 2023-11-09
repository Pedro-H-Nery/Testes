## Units -> Edit

### 1. Editar uma unidade

### Requisição para API

#### 1. Rota da API

PUT -> `api/units/{Unit_id}`

#### 2. Parâmetros e Suas Utilidades

Unit_id\*: o id da unidade que será editada

#### 3. Exemplo de Requisição

PUT -> `api/units/1`

Body:

```json
{
  "name": "Exemplo 1 Alterado",
  "acronym": "[EX1A]",
  "latitude": "5.079222",
  "longitude": "-50.761417"
}
```

OBS: os atributos `acronym`, `latitude` e `longitude` são opcionais

### Retorno da API

#### Sucesso

Retorna um json contendo as informações da unidade que foi editada e uma mensagem de sucesso.

**Ex**:

```json
{
  "App\\Model\\Entity\\Unit": {
    "id": 1,
    "company_id": 1,
    "name": "Exemplo 1 Alterado",
    "acronym": "[EX1A]",
    "latitude": "5.079222",
    "longitude": "-50.761417",
    "created": "2023-11-09T12:41:30-03:00",
    "modified": "2023-11-09T12:43:50-03:00",
    "active": true,
    "deleted": null,
    "is_ticket": false,
    "due_days": null,
    "created_by": 3,
    "deleted_by": null
  },
  "message": "Sucesso ao editar Unidade!",
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando editar uma unidade da empresa que participa

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Você não tem permissão para acessar esse recurso!"
    }
    ```

2.  Se a unidade passada como parâmetro não for encontrada

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Registro não encontrado!"
    }
    ```

3.  Se acontecer algum erro ao tentar salvar a unidade passada como parâmetro

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Erro ao editar Unidade!"
    }
    ```

4.  Se acontecer algum outro erro ao tentar achar a unidade passada como parâmetro

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Erro interno no sistema"
    }
    ```
