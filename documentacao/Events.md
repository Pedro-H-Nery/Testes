## Events

### Index

#### Rota da API

GET -> `api/events`
GET -> `api/events/{Users_ids}`

#### Parâmetros e Suas Utilidades

Users_ids: lista com um ou mais usuários que será vista a agenda. Se não for especifícado a agenda do usuário atual será retornada

#### Retorno da API

**Sucesso**:

**Erro(s)**:

### Add

#### Rota da API

POST -> `api/events`

#### Parâmetros e Suas Utilidades

Sem parâmetros

#### Retorno da API

**Sucesso**:

**Erro(s)**:

### View

#### Rota da API

GET -> `api/events/{User_id}/{Model_type}/{Model_id}`

#### Parâmetros e Suas Utilidades

User_id\*: id do usuário que está tentando ver um ítem da agenda
Model_type\*: nome do modelo do ítem da agenda que o usuário está tentando ver(Ex: action ou holiday)
Model_id\*: id do ítem da agenda que o usuário está tentando ver

#### Retorno da API

**Sucesso**:

**Erro(s)**:

### Edit

#### Rota da API

POST -> `api/events/{Event_id}`

#### Parâmetros e Suas Utilidades

Event_id\*: id do evento que será editado

#### Retorno da API

**Sucesso**:

**Erro(s)**:

### Delete

#### Rota da API

DELETE -> `api/events/{Event_id}`

#### Parâmetros e Suas Utilidades

Event_id\*: id do evento que será deletado

#### Retorno da API

**Sucesso**:

**Erro(s)**:
