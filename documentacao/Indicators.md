## Indicators

### Index

#### Rota da API

GET -> `api/indicators`
GET -> `api/indicators?list_all=basic`

#### Parâmetros e Suas Utilidades

Modo de retorno das informações: Para receber um array com todos os indicadores da empresa do usuário onde o id do indicador é a chave e o nome do indicador é o valor é possível definir na query o parametro `list_all` como `basic`.

#### Retorno da API

**Sucesso**: Retorna uma lista com as informações de todos os indicadores da empresa.

**Erro(s)**: Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando ver os indicadores da empresa que participa será retornada a mensagem de erro: `Você não tem permissão para acessar este recurso.`

### Add

#### Rota da API

POST -> `api/indicators`

#### Parâmetros e Suas Utilidades

Sem parâmetros

#### Retorno da API

**Sucesso**: Será criada um novo indicador com as informações específicadas pelo usuário e será retornada a mensagem de sucesso: `Sucesso ao adicionar Indicador!`.

**Erro(s)**: Se o usuário não tiver um nível de permissão igual ou superior Gestor será retornada a mensagem de erro: `Você não tem permissão para acessar este recurso.`. Se acontecer algum erro ao tentar salvar o indicador será retornada a mensagem de erro: `Erro ao adicionar Indicador.`.

### Edit

#### Rota da API

POST -> `api/indicators/{Indicator_id}`

#### Parâmetros e Suas Utilidades

Indicator_id\*: o id do indicador que terá suas informações alteradas

#### Retorno da API

**Sucesso**: O indicador passado como parâmetro terá suas informações alteradas de acordo com o que foi específicado pelo usuário e será retornada a mensagem de sucesso: `Sucesso ao editar Indicador.`.

**Erro(s)**: Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando editar um indicador da empresa que participa será retornada a mensagem de erro: `Você não tem permissão para acessar esse recurso!` Se o indicador passado como parâmetro não for encontrado será retornada a mensagem de erro: `Registro não encontrado!`. Se acontecer algum erro ao tentar salvar o indicador passado como parâmetro será retornada a mensagem de erro: `Erro ao editar Indicador`. Se acontecer algum outro erro ao tentar achar o indicador passado como parâmetro será retornada a mensagem de erro: `Erro interno no sistema`.

### Delete

#### Rota da API

DELETE -> `api/indicators/{Indicator_id}`

#### Parâmetros e Suas Utilidades

Indicator_id\*: o id do indicador que será deletado

#### Retorno da API

**Sucesso**: O indicador será deletado da empresa, não será possível acessar ou ver ele e será retornada a mensagem de sucesso: `Sucesso ao deletar Indicador.`.

**Erro(s)**: Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando deletar um indicador da empresa que participa será retornada a mensagem de erro: `Você não tem permissão para acessar esse recurso!` Se o indicador passado como parâmetro não for encontrada será retornada a mensagem de erro: `Registro não encontrado!`. Se acontecer algum erro ao tentar deletar o indicador passado como parâmetro será retornada a mensagem de erro: `Erro ao deletar Indicador!`. Se acontecer algum outro erro ao tentar achar o indicador passado como parâmetro será retornada a mensagem de erro: `Erro interno no sistema`.
