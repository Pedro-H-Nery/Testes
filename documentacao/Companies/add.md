## Companies -> Add

### 1. Adicionar uma empresa

### Requisição para API

#### 1. Rota da API

POST -> `api/companies`

#### 2. Parâmetros e Suas Utilidades

Sem parâmetros

#### 3. Exemplo de Requisição

POST -> `api/companies`

Body:

```json
{
  "name": "Empresa 1",
  "plan_id": 1,
  "price": 222,
  "recurrency": 3,
  "discount": 40,
  "cnpj_cpf": 543345343543,
  "street": "teste",
  "cep": 343524323,
  "number": 23,
  "district": "teste",
  "city": "teste",
  "state": "teste",
  "corporate_name": "teste",
  "financial_responsible_name": "teste",
  "financial_responsible_cpf_cnpj": 334325346,
  "financial_responsible_telephone": 546345243,
  "financial_responsible_cep": 3543643653,
  "financial_responsible_street": "teste",
  "financial_responsible_number": 243,
  "financial_responsible_district": "teste",
  "financial_responsible_city": "teste",
  "financial_responsible_state": "teste",
  "active": 1
}
```

OBS: os atributos `name`, `plan_id`, `recurrency` e `active` são obrigatórios e os outros são opcionais.

### Retorno da API

#### Sucesso

Retorna um json com as informações da empresa que foi adicionada no sistema e uma mensagem de sucesso.

**Ex**:

```json
{
  "App\\Model\\Entity\\Company": {
    "id": 1,
    "name": "Empresa 1",
    "plan_id": 1,
    "price": "222",
    "recurrency": 3,
    "discount": 40,
    "cnpj_cpf": "543345343543",
    "street": "teste",
    "cep": "343524323",
    "number": "23",
    "district": "teste",
    "city": "teste",
    "state": "teste",
    "corporate_name": "teste",
    "financial_responsible_name": "teste",
    "financial_responsible_cpf_cnpj": "334325346",
    "financial_responsible_telephone": "546345243",
    "financial_responsible_cep": "3543643653",
    "financial_responsible_street": "teste",
    "financial_responsible_number": "243",
    "financial_responsible_district": "teste",
    "financial_responsible_city": "teste",
    "financial_responsible_state": "teste",
    "active": true,
    "created": "2023-11-17T12:04:25-03:00",
    "modified": "2023-11-17T12:04:25-03:00",
    "created_by": 3
  },
  "message": "A compania Empresa 1 foi salva.",
  "status": 1
}
```

#### Erro(s)

1.  Se o usuário não tiver nível de permissão igual a Master

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "Você não tem permissão para acessar este recurso."
    }
    ```

2.  Se acontecer algum erro ao tentar salvar a empresa

    **Ex**:

    ```json
    {
      "status": 0,
      "message": "A compania {Nome da empresa} não pode ser salva. Por favor , tente novamente."
    }
    ```
