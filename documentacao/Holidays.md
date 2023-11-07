## Holidays

### Index

#### Rota da API

GET -> `api/holidays`
GET -> `api/holidays?list_all=basic`

#### Parâmetros e Suas Utilidades

Modo de retorno das informações: Para receber um array com todas as ausências da empresa do usuário onde o id da ausência é a chave e o motivo da ausência é o valor é possível definir na query o parametro `list_all` como `basic`.

#### Retorno da API

**Sucesso**: Retorna uma lista com as informações de todas as ausências da empresa.

**Erro(s)**:
Erro de permissão: `Você não tem permissão para acessar este recurso.` => Usuário não é master ou então não é gestor ou superior tentando ver os feriados da empresa que participa.

### Add

#### Rota da API

POST -> `api/holidays`

#### Parâmetros e Suas Utilidades

Sem parâmetros

#### Retorno da API

**Sucesso**: Será criada uma nova ausência com as informações específicadas pelo usuário e será retornada a mensagem de sucesso: `A ausência foi salva.`.

**Erro(s)**:
Erro de permissão: `Você não tem permissão para acessar este recurso.` => Usuário não é gestor ou superior.
Erro de data: `A data de início precisa ser antes da data de fim.` => Data de início maior que a data de fim.
Erro ao salvar: `A ausência não pôde ser salva. Por favor, tente novamente.`.

### Edit

#### Rota da API

POST -> `api/holidays/{Holiday_id}`

#### Parâmetros e Suas Utilidades

Holiday_id\*: o id da ausência que terá suas informações alteradas ## Exemplo de requisição

#### Retorno da API

**Sucesso**: A ausência passada como parâmetro terá suas informações alteradas de acordo com o que foi específicado pelo usuário e será retornada a mensagem de sucesso: `A ausência foi editada com sucesso.`.

**Erro(s)**:
Erro de permissão: `Você não tem permissão para acessar este recurso.` => Usuário não é master ou então não é gestor ou superior tentando editar uma ausência da empresa que participa.
Erro de data: `A data de início precisa ser antes da data de fim.` => Data de início maior que a data de fim.
Erro ao salvar: `A ausência não pôde ser editada. Por favor, tente novamente.`.

### Delete

#### Rota da API

DELETE -> `api/holidays/{Holiday_id}`

#### Parâmetros e Suas Utilidades

Holiday_id\*: o id da ausência que será deletada

#### Retorno da API

**Sucesso**: A ausência será deletada da empresa, não será possível acessar ou ver ela e será retornada a mensagem de sucesso: `A ausência foi removida com sucesso.`.

**Erro(s)**:
Erro de permissão: `Você não tem permissão para acessar esse recurso!` => Usuário não é master ou então não é gestor ou superior tentando deletar uma ausência da empresa que participa.
Erro de registro não encontrado: `Registro não encontrado!`
Erro de data: `A data de início precisa ser antes da data de fim.` => Data de início maior que a data de fim.
Erro ao deletar: `A ausência não pôde ser removida. Por favor, tente novamente.`.
Erro desconhecido ao tentar encontrar o registro: `Erro interno no sistema`.
