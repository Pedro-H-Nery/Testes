## Holidays -> Index

### 1. Listagem de todas as ausências

### Requisição para API

#### 1. Rota da API

GET-> `api/holidays`

#### 2. Parâmetros e Suas Utilidades

Sem parâmetros

#### 3. Exemplo de Requisição

GET -> `api/holidays`

Body:

```json
{}
```

### Retorno da API

#### Sucesso

Retorna um json contendo uma lista com as ausências da empresa atual, suas informações e também informações da(s) unidade(s) e/ou do usuário associado as ausências.

**Ex**:

```json
{
  "holidays": [
    {
      "id": 1,
      "reason": "Motivo",
      "start": "2023-11-20",
      "end": "2023-11-22",
      "type": 3,
      "user_id": 1,
      "company_id": 1,
      "created": "2023-11-18T13:43:39-03:00",
      "modified": "2023-11-18T13:51:18-03:00",
      "deleted": null,
      "created_by": 3,
      "deleted_by": null,
      "user": {
        "id": 1,
        "unit_id": 1,
        "sector_id": 1,
        "job_id": 3,
        "name": "teste",
        "email": "teste",
        "phone": "6536352434",
        "admission": "2000-10-10",
        "photo_url": "teste.jpg",
        "company_id": 1,
        "status": true,
        "token": "teste",
        "active": true,
        "is_visitor": false,
        "company_name": null,
        "created": "2021-11-13T14:22:08-03:00",
        "modified": "2023-06-23T14:05:36-03:00",
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
        "auth_type": 5,
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
        "created_by": null,
        "deleted_by": null
      },
      "holidays_in_units": []
    },
    {
      "id": 2,
      "reason": "Motivo 2",
      "start": "2023-12-25",
      "end": "2023-12-25",
      "type": 3,
      "user_id": null,
      "company_id": 1,
      "created": "2023-05-24T17:02:59-03:00",
      "modified": "2023-10-16T13:54:09-03:00",
      "deleted": null,
      "created_by": null,
      "deleted_by": null,
      "user": null,
      "holidays_in_units": [
        {
          "holiday_id": 2,
          "unit_id": 1,
          "unit": {
            "id": 1,
            "company_id": 1,
            "name": "teste",
            "acronym": null,
            "latitude": null,
            "longitude": null,
            "created": "2023-07-06T18:25:16-03:00",
            "modified": "2023-07-06T18:30:36-03:00",
            "active": true,
            "deleted": null,
            "is_ticket": false,
            "due_days": 0,
            "created_by": 3,
            "deleted_by": null
          }
        }
      ]
    }
  ],
  "holiday": {
    "company_id": 1
  },
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando ver as ausências da empresa que participa

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Você não tem permissão para acessar este recurso."
    }
    ```

### 2. Listagem com o nome e id das ausências

### Requisição para API

#### 1. Rota da API

GET -> `api/holidays?list_all=basic`

#### 2. Parâmetros e Suas Utilidades

list_all: recebe a palavra `basic` para indicar que a listagem é de apenas o id e o nome das ausências

#### 3. Exemplo de Requisição

GET -> `api/holidays?list_all=basic`

Body:

```json
{}
```

### Retorno da API

#### Sucesso

Retorna um json contendo uma lista com o id e o nome de cada uma das ausências da empresa atual.
**Ex**:

```json
{
  "holidays": {
    "1": "Motivo",
    "2": "Motivo 2"
  },
  "holiday": {
    "company_id": 1
  },
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando ver as ausências da empresa que participa

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Você não tem permissão para acessar este recurso."
    }
    ```
