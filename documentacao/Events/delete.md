## Events -> Delete

### 1. Deletar um compromisso

### Requisição para API

#### 1. Rota da API

DELETE -> `api/events/{Event_id}`

#### 2. Parâmetros e Suas Utilidades

Event_id\*: o id do compromisso que será deletado

#### 3. Exemplo de Requisição

DELETE -> `api/events/1`

Body:

```json
{}
```

### Retorno da API

#### Sucesso

Retorna um json contendo as informações do compromisso que foi deletado e uma mensagem de sucesso.

**Ex**:

```json
{
  "App\\Model\\Entity\\Event": {
    "id": 1,
    "company_id": 1,
    "user_id": 1,
    "name": "Evento 1",
    "start": "2023-11-25T10:11:00-03:00",
    "end": "2023-11-26T12:11:00-03:00",
    "local": "teste",
    "description": "",
    "allday": false,
    "privacy": false,
    "created": "2023-10-06T14:32:06-03:00",
    "modified": "2023-11-24T10:05:45-03:00",
    "deleted": null,
    "created_by": 1,
    "deleted_by": 1
  },
  "message": "Sucesso ao deletar Evento!",
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando deletar um compromisso não privado de um usuário da empresa que participa ou então não estiver tentando deletar um compromisso que ele criou

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Você não tem permissão para acessar esse recurso!"
    }
    ```

2.  Se o compromisso passado como parâmetro não for encontrado

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Registro não encontrado!"
    }
    ```

3.  Se acontecer algum erro ao tentar deletar o compromisso passado como parâmetro

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Erro ao deletar Compromisso!"
    }
    ```

4.  Se acontecer algum outro erro ao tentar achar o compromisso passado como parâmetro

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Erro interno no sistema"
    }
    ```
