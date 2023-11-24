## Users -> Select Users

### 1. Buscar um termo entre o nome dos usuários de uma empresa

### Requisição para API

#### 1. Rota da API

GET -> `api/users/select-users?term[term]={Termo}&company_id={Company_id}`

#### 2. Parâmetros e Suas Utilidades

Termo\*: letras que serão buscadas entre todos os usuários de uma determinada empresa para saber aqueles que possuem as letras juntas em alguma parte de seus nomes
Company_id \*: id da empresa dos usuários em que será buscado o termo

#### 3. Exemplo de Requisição

GET -> `api/users/select-users?term[term]=Teste&company_id=1`

Body:

```json
{}
```

### Retorno da API

#### Sucesso

Retorna uma lista com o id e o nome dos usuários que possuem o termo especificado em alguma parte de seus nomes.

**Ex**:

```json
[
  {
    "id": 1,
    "text": "[Un1] - Teste 1"
  },
  {
    "id": 2,
    "text": "[Un1] - Usuário Teste 2"
  },
  {
    "id": 3,
    "text": "[Un1] - [Set1] - Teste 3"
  }
]
```

#### Erro(s)

Não possui erros possíveis.
