## Holidays -> Add

### 1. Adicionar nova ausência para uma, várias ou todas as unidades

### Requisição para API

#### 1. Rota da API

POST -> `api/holidays`

#### 2. Parâmetros e Suas Utilidades

Sem parâmetros

#### 3. Exemplo de Requisição

POST -> `api/holidays`

Body:

```json
{
  "reason": "Motivo",
  "type": "3",
  "start": "2023-11-20",
  "end": "2023-11-22",
  "affected": "1",
  "user_id": "1",
  "units": ["1", "2"]
}
```

OBS: Para que a ausência seja válida para unidades é necessário definir o atributo `affected` para `1` para que o array de `units` seja considerado na criação da ausência. Pode ser selecionado para receber a ausência uma ou várias unidades e para que a ausência seja válida para todas as unidades da empresa então o array `units` precisa estar sem elementos.

### Retorno da API

#### Sucesso

Retorna um json contendo as informações da ausência que foi criada, das unidades em que ela é válida e uma mensagem de sucesso. Se o array `holidays_in_units` estiver vazio e `user_id ` estiver `null` então a ausência é válida para todas as unidades da empresa.

**Ex**:

```json
{
  "App\\Model\\Entity\\Holiday": {
    "company_id": 1,
    "reason": "Motivo",
    "type": 3,
    "start": "2023-11-20",
    "end": "2023-11-22",
    "user_id": null,
    "holidays_in_units": [
      {
        "unit_id": "1",
        "holiday_id": 1
      },
      {
        "unit_id": "2",
        "holiday_id": 1
      }
    ],
    "created": "2023-11-18T13:43:39-03:00",
    "modified": "2023-11-18T13:43:39-03:00",
    "created_by": 3,
    "id": 1
  },
  "message": "A ausência foi salva.",
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário não tiver um nível de permissão igual ou superior a Gestor

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

### 2. Adicionar nova ausência para um usuário

### Requisição para API

#### 1. Rota da API

POST -> `api/holidays`

#### 2. Parâmetros e Suas Utilidades

Sem parâmetros

#### 3. Exemplo de Requisição

POST -> `api/holidays`

Body:

```json
{
  "reason": "Motivo",
  "type": "3",
  "start": "2023-11-24",
  "end": "2023-11-28",
  "affected": "0",
  "user_id": "1",
  "units": ""
}
```

OBS: Para que a ausência seja válida para um usuário é necessário definir o atributo `affected` para `0` para que o `user_id` seja considerado na criação da ausência

### Retorno da API

#### Sucesso

Retorna um json contendo as informações da ausência que foi criada e uma mensagem de sucesso.

**Ex**:

```json
{
  "App\\Model\\Entity\\Holiday": {
    "company_id": 1,
    "reason": "Motivo",
    "type": 3,
    "start": "2023-11-24",
    "end": "2023-11-28",
    "user_id": 1,
    "created": "2023-11-18T13:17:18-03:00",
    "modified": "2023-11-18T13:17:18-03:00",
    "created_by": 3,
    "id": 2
  },
  "message": "A ausência foi salva.",
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário não tiver um nível de permissão igual ou superior a Gestor

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
