## Users -> Delete

### 1. Deletar um usuário

### Requisição para API

#### 1. Rota da API

DELETE -> `api/users/{User_id}`

#### 2. Parâmetros e Suas Utilidades

User_id\*: id do usuário que será deletado

#### 3. Exemplo de Requisição

DELETE -> `api/users/1`

Body:

```json
{}
```

### Retorno da API

#### Sucesso

Retorna um json contendo as informações do usuário que foi deletado e uma mensagem de sucesso.

**Ex**:

```json
{
  "App\\Model\\Entity\\User": {
    "id": 1,
    "unit_id": 1,
    "sector_id": 1,
    "job_id": 1,
    "name": "Teste 01 Alterado",
    "email": "teste01alterado@gmail.com",
    "phone": "4567634344",
    "admission": "2000-11-14",
    "photo_url": "semfoto.png",
    "company_id": 1,
    "status": true,
    "token": null,
    "active": true,
    "is_visitor": false,
    "company_name": null,
    "created": "2023-11-18T17:33:05-03:00",
    "modified": "2023-11-20T12:12:10-03:00",
    "is_actions": 1,
    "is_meets": 1,
    "is_checklists": 1,
    "is_forms": 1,
    "is_calendars": 1,
    "is_anomalies": 1,
    "is_tickets": 1,
    "is_trainings": 1,
    "is_users": 1,
    "is_files": 1,
    "is_events": 1,
    "auth_type": 2,
    "calendar_share_code": null,
    "deleted": null,
    "is_ticket": true,
    "desactived": null,
    "about": null,
    "linkedin": null,
    "facebook": null,
    "twitter": null,
    "instagram": null,
    "front_cover": null,
    "photo_foreground_url": null,
    "created_by": 3,
    "deleted_by": 3
  },
  "message": "Usuário Teste 01 Alterado deletado com sucesso.",
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário não for Master ou então não tiver um nível de permissão igual ou superior a Gestor e estiver tentando deletar um usuário com nível de permissão menor e que é da empresa que participa

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Você não tem permissão para deletar este usuário."
    }
    ```

2.  Se acontecer algum erro ao tentar salvar o usuário ou algum erro ao tentar criar o usuário com as informações enviadas

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Erro ao deletar o usuário {Nome do usuário}"
    }
    ```
