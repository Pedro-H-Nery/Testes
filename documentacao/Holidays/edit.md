## Holidays -> Edit

### 1. Editar uma ausência

### Requisição para API

#### 1. Rota da API

PUT -> `api/holidays/{Holiday_id}`

#### 2. Parâmetros e Suas Utilidades

Holiday_id\*: o id da ausência que será editada

#### 3. Exemplo de Requisição

PUT -> `api/holidays/1`

Body:

```json
{
  "reason": "Motivo",
  "type": "3",
  "start": "2023-11-20",
  "end": "2023-11-22",
  "affected": "0",
  "user_id": "1",
  "units": []
}
```

OBS: Se deseja editar uma ausência associada a um usuário para que ela seja associada a uma ou várias unidades é necessário especificar o atributo `affected` para `1` e especificar as unidades no array `units`. Se deseja editar uma ausência associada a uma ou várias unidades para que ela seja associada a um usuário é necessário especificar o atributo `affected` para `0` e especificar o usuário no atributo `user_id`.

### Retorno da API

#### Sucesso

Retorna um json contendo as informações da ausência que foi editada, das unidades em que ela é válida e as informações das unidades ou então o usuário que é afetado por ela e uma mensagem de sucesso. Se o array `holidays_in_units` estiver vazio e `user_id ` estiver `null` então a ausência é válida para todas as unidades da empresa. Se `user_id` não estiver como `null` então a ausência é para um usuário independente se existe uma ou mais unidades associadas a ausência.

**Ex**:

```json
{
  "App\\Model\\Entity\\Holiday": {
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
    "holidays_in_units": [
      {
        "holiday_id": 1,
        "unit_id": 1,
        "unit": {
          "id": 1,
          "company_id": 1,
          "name": "teste",
          "acronym": "teste",
          "latitude": null,
          "longitude": null,
          "created": null,
          "modified": "2023-10-20T15:37:40-03:00",
          "active": true,
          "deleted": null,
          "is_ticket": true,
          "due_days": 25,
          "created_by": null,
          "deleted_by": null
        }
      },
      {
        "holiday_id": 1,
        "unit_id": 2,
        "unit": {
          "id": 2,
          "company_id": 1,
          "name": "teste",
          "acronym": null,
          "latitude": null,
          "longitude": null,
          "created": "2023-05-26T12:47:42-03:00",
          "modified": "2023-07-06T18:25:45-03:00",
          "active": true,
          "deleted": null,
          "is_ticket": true,
          "due_days": 330,
          "created_by": null,
          "deleted_by": null
        }
      }
    ]
  },
  "message": "A ausência foi editada com sucesso.",
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando editar uma ausência da empresa e da unidade que participa

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Você não tem permissão para acessar este recurso."
    }
    ```

2.  Se a data de início da ausência que for maior que a data de fim

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "A data de início precisa ser antes da data de fim."
    }
    ```

3.  Se acontecer algum erro ao tentar salvar a ausência

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "A ausência não pôde ser salva. Por favor, tente novamente."
    }
    ```
