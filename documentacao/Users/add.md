## Users -> Add

### 1. Adicionar novo usuário

### Requisição para API

#### 1. Rota da API

POST -> `api/users`

#### 2. Parâmetros e Suas Utilidades

Sem parâmetros

#### 3. Exemplo de Requisição

POST -> `api/users`

Body:

```json
{
  "id": "",
  "name": "Teste 01",
  "email": "teste01@gmail.com",
  "password": "teste01",
  "phone": "443432434434",
  "sector_id": "1",
  "admission": "2023-11-15",
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

OBS: os atributos `id`, `name`, `email`, `password`, `sector_id`, `job_id`, `unit_id`, `auth_type`, `status`, `is_ticket`, `is_events`, `is_actions`, `is_meets`, `is_checklists`, `is_forms`, `is_calendars`, `is_anomalies`, `is_tickets`, `is_trainings`, `is_users`, `is_files`, são obrigatórios e os outros são opcionais.

### Retorno da API

#### Sucesso

Retorna um json contendo as informações do usuário que foi criado e uma mensagem de sucesso.

**Ex**:

```json
{
  "App\\Model\\Entity\\User": {
    "name": "Teste 01",
    "email": "teste01@gmail.com",
    "phone": "443432434434",
    "sector_id": 1,
    "admission": "2023-11-15",
    "job_id": 1,
    "unit_id": 1,
    "auth_type": 2,
    "status": true,
    "is_ticket": true,
    "is_events": 1,
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
    "company_id": 1,
    "photo_url": "semfoto.png",
    "created": "2023-11-18T17:03:57-03:00",
    "modified": "2023-11-18T17:03:57-03:00",
    "created_by": 3,
    "id": 1
  },
  "message": "Usuário cadastrado com sucesso!",
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário não tiver um nível de permissão igual ou superior a Gestor

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Você não tem permissão para adicionar usuários."
    }
    ```

2.  Se acontecer algum erro ao tentar salvar o usuário ou algum erro ao tentar criar o usuário com as informações enviadas

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Erro ao cadastrar o usuário #{Nome do usuário}. Tente novamente"
    }
    ```
