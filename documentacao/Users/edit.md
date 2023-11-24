## Users -> Edit

### 1. Editar um usuário

### Requisição para API

#### 1. Rota da API

PUT -> `api/users/{User_id}`

#### 2. Parâmetros e Suas Utilidades

User_id\*: id do usuário que será editado

#### 3. Exemplo de Requisição

PUT -> `api/users/1`

Body:

```json
{
  "id": "1",
  "name": "Teste 01 Alterado",
  "email": "teste01alterado@gmail.com",
  "password": "teste01.",
  "phone": "4567634344",
  "sector_id": "1",
  "admission": "2000-11-14",
  "job_id": "1",
  "unit_id": "1",
  "auth_type": "2",
  "status": "1",
  "is_ticket": "1",
  "units": ["1", "2"],
  "sectors_tickets": ["1", "2"],
  "is_events": "1",
  "is_actions": "1",
  "is_meets": "1",
  "is_checklists": "1",
  "is_forms": "1",
  "is_calendars": "1",
  "is_anomalies": "1",
  "is_tickets": "1",
  "is_trainings": "1",
  "is_users": "1",
  "is_files": "1"
}
```

OBS: Todos os atributos são opcionais e se nenhum for enviado será retornado as informações do usuário passado como parâmetro. Não é possível que dois usuários tenham o mesmo email.

### Retorno da API

#### Sucesso

Retorna um json contendo as informações do usuário que foi editado e uma mensagem de sucesso.

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
    "phone": "443432434434",
    "admission": "2000-11-14",
    "photo_url": "semfoto.png",
    "company_id": 1,
    "status": true,
    "token": null,
    "active": true,
    "is_visitor": false,
    "company_name": null,
    "created": "2023-11-18T17:34:08-03:00",
    "modified": "2023-11-20T08:47:14-03:00",
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
    "deleted_by": null,
    "users_in_units_tickets": [],
    "users_in_sectors_tickets": [
      {
        "sector_id": 1,
        "user_id": 1
      },
      {
        "sector_id": 2,
        "user_id": 1
      }
    ],
    "users_in_units": [
      {
        "unit_id": 1,
        "user_id": 1
      },
      {
        "unit_id": 2,
        "user_id": 1
      }
    ],
    "users_master_companies": []
  },
  "message": "Usuário atualizado com sucesso!",
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário não for Master ou então não tiver um nível de permissão igual ou superior a Gestor e estiver tentando editar um usuário com nível de permissão menor e que é da empresa que participa ou então não for o usuário que foi passado como parâmetro

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Você não tem permissão para editar esse usuário."
    }
    ```

2.  Se acontecer algum erro ao tentar salvar o usuário

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Erro ao editar o usuário #{Nome do usuário}. Tente novamente"
    }
    ```
