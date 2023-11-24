## Users -> Profile Edit

### 1. Editar o perfil de um usuário

### Requisição para API

#### 1. Rota da API

PUT -> `api/users/perfil-edit/{User_id}`

#### 2. Parâmetros e Suas Utilidades

User_id\*: id do usuário que se deseja editar o perfil

#### 3. Exemplo de Requisição

PUT -> `api/users/perfil-edit/1`

Body:

```json
{
  "photo_foreground_url_file": "",
  "photo_url_file": "",
  "linkedin": "",
  "facebook": "",
  "instagram": "",
  "twitter": "",
  "name": "Usuário 1 Alterado",
  "phone": "(88)99999-6666",
  "email": "teste@gmail.com",
  "about": ""
}
```

OBS: os atributos `name`, `email`, `photo_foreground_url_file` e `photo_url_file` são obrigatórios e os outros são opcionais. Não é possível que dois usuários tenham o mesmo email.

### Retorno da API

#### Sucesso

Retorna um json contendo as informações do usuário que teve seu perfil editado e uma mensagem de sucesso.

**Ex**:

```json
{
  "App\\Model\\Entity\\User": {
    "id": 1,
    "unit_id": 1,
    "sector_id": 1,
    "job_id": 1,
    "name": "Usuário 1 Alterado",
    "email": "teste@gmail.com",
    "phone": "(88)99999-6666",
    "admission": "2001-12-01",
    "photo_url": "teste.jpg",
    "company_id": 1,
    "status": true,
    "token": "rwrtcu349347yemt8yyxr64t6tx36t8m6cy34ym3xm8z",
    "active": true,
    "is_visitor": false,
    "company_name": null,
    "created": "2021-11-13T14:32:11-03:00",
    "modified": "2023-11-24T09:33:52-03:00",
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
    "auth_type": 1,
    "calendar_share_code": null,
    "deleted": null,
    "is_ticket": true,
    "desactived": null,
    "about": "",
    "linkedin": "",
    "facebook": "",
    "twitter": "",
    "instagram": "",
    "front_cover": null,
    "photo_foreground_url": null,
    "created_by": null,
    "deleted_by": null,
    "job": null
  },
  "message": "Usuário alterado com sucesso!",
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário não for Master ou então não tiver um nível de permissão igual ou superior a Gestor e estiver tentando editar o perfil de um usuário da empresa que participa ou não estiver tentando editar o próprio perfil

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Você não tem permissão para acessar este recurso."
    }
    ```

2.  Se acontecer algum erro ao tentar salvar o perfil do usuário

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Erro ao alterar o usuário #{Nome do usuário}. Tente novamente."
    }
    ```
