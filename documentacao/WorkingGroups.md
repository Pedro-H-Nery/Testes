## Working Groups

### Index

#### Rota da API

GET -> `api/working-groups`
GET -> `api/working-groups?list_all=basic`

#### Parâmetros e Suas Utilidades

Modo de retorno das informações: Para receber uma lista com todos os grupos de trabalho da empresa do usuário onde cada grupos de trabalho contém informações sobre seu id, nome e o nome dos usuários que fazem parte dele é possível definir na query o parametro `list_all` como `basic`.

#### Retorno da API

**Sucesso**: Retorna uma lista com as informações de todos os grupos de trabalho da empresa.

**Erro(s)**: Se o usuário não for um usuário de nível de permissão igual ou superior a Gestor tentando ver os grupos de trabalho da empresa que participa será retornada a mensagem de erro: `Você não tem permissão para acessar este recurso.`

### Add

#### Rota da API

POST -> `api/working-groups`

#### Parâmetros e Suas Utilidades

Sem parâmetros

#### Retorno da API

**Sucesso**: Será criada um novo grupo de trabalho com as informações e os participantes específicados pelo usuário e será retornada a mensagem de sucesso: `Sucesso ao adicionar Grupo de Trabalho!`.

**Erro(s)**: Se o usuário não tiver um nível de permissão igual ou superior Gestor será retornada a mensagem de erro: `Você não tem permissão para acessar este recurso.`. Se acontecer algum erro ao tentar salvar o objetivo será retornada a mensagem de erro: `Erro ao adicionar Grupo de Trabalho!`.

### Edit

#### Rota da API

POST -> `api/working-groups/{Working_Group_id}`

#### Parâmetros e Suas Utilidades

Working_Group_id\*: o id do grupo de trabalho que terá suas informações alteradas

#### Retorno da API

**Sucesso**: O grupo de trabalho passado como parâmetro terá suas informações e/ou participantes alterados de acordo com o que foi específicado pelo usuário e será retornada a mensagem de sucesso: `Sucesso ao editar Grupo de Trabalho!`.

**Erro(s)**: Se o usuário não for um usuário de nível de permissão igual ou superior a Gestor tentando editar um grupo de trabalho da empresa que participa será retornada a mensagem de erro: `Você não tem permissão para acessar esse recurso!`. Se acontecer algum erro ao tentar salvar o grupo de trabalho passado como parâmetro será retornada a mensagem de erro: `Erro ao editar Grupo de Trabalho!`.

### Delete

#### Rota da API

DELETE -> `api/working-groups/{Working_Group_id}`

#### Parâmetros e Suas Utilidades

Working_Group_id\*: o id do grupo de trabalho que será deletado

#### Retorno da API

**Sucesso**: O grupo de trabalho será deletado da empresa, não será possível acessar ou ver ele e será retornada a mensagem de sucesso: `Sucesso ao deletar Grupo de Trabalho!`.

**Erro(s)**: Se o usuário não for um usuário de nível de permissão igual ou superior a Gestor tentando deletar um grupo de trabalho da empresa que participa será retornada a mensagem de erro: `Você não tem permissão para acessar esse recurso!`. Se acontecer algum erro ao tentar deletar o grupo de trabalho passado como parâmetro será retornada a mensagem de erro: `Erro ao deletar Objetivo!`.
