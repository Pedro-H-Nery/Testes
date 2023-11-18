## Holidays -> Delete

### 1. Deletar uma ausência

### Requisição para API

#### 1. Rota da API

DELETE -> `api/holidays/{Holiday_id}`

#### 2. Parâmetros e Suas Utilidades

Holiday_id\*: o id da ausência que será deletada

#### 3. Exemplo de Requisição

DELETE -> `api/holidays/1`

Body:

```json
{}
```

### Retorno da API

#### Sucesso

Retorna um json contendo as informações da ausência que foi deletada e uma mensagem de sucesso.

**Ex**:

```json
{
  "App\\Model\\Entity\\Holiday": {
    "id": 1,
    "reason": "Ausência 1",
    "start": "2023-06-13",
    "end": "2023-06-14",
    "type": 3,
    "user_id": null,
    "company_id": 1,
    "created": "2023-05-24T17:02:59-03:00",
    "modified": "2023-11-18T13:01:29-03:00",
    "deleted": null,
    "created_by": null,
    "deleted_by": 3
  },
  "message": "A ausência foi removida com sucesso.",
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando deletar uma ausência da empresa e da unidade que participa

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Você não tem permissão para acessar esse recurso!"
    }
    ```

2.  Se a ausência passada como parâmetro não for encontrada

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Registro não encontrado!"
    }
    ```

3.  Se acontecer algum erro ao tentar deletar a ausência passada como parâmetro

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "A ausência não pôde ser removida. Por favor, tente novamente."
    }
    ```

4.  Se acontecer algum outro erro ao tentar achar a ausência passada como parâmetro

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Erro interno no sistema"
    }
    ```
