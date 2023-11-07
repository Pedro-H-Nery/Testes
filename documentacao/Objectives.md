## Objectives

### Index

#### Rota da API

GET -> `api/objectives`
GET -> `api/objectives?list_all=basic`

#### Parâmetros e Suas Utilidades

Modo de retorno das informações: Para receber um array com todos os objetivos da empresa do usuário onde o id do objetivo é a chave e o nome do objetivo é o valor é possível definir na query o parametro `list_all` como `basic`.

#### Retorno da API

**Sucesso**: Retorna uma lista com as informações de todos os objetivos da empresa.

**Erro(s)**: Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando ver os objetivos da empresa que participa será retornada a mensagem de erro: `Você não tem permissão para acessar este recurso.`

### Add

#### Rota da API

POST -> `api/objectives`

#### Parâmetros e Suas Utilidades

Sem parâmetros

#### Retorno da API

**Sucesso**: Será criada um novo objetivo com as informações específicadas pelo usuário e será retornada a mensagem de sucesso: `Sucesso ao adicionar Objetivo!`.

**Erro(s)**: Se o usuário não tiver um nível de permissão igual ou superior Gestor será retornada a mensagem de erro: `Você não tem permissão para acessar este recurso.`. Se acontecer algum erro ao tentar salvar o objetivo será retornada a mensagem de erro: `Erro ao adicionar Objetivo.`.

### Edit

#### Rota da API

POST -> `api/objectives/{Objective_id}`

#### Parâmetros e Suas Utilidades

Objective_id\*: o id do objetivo que terá suas informações alteradas

#### Retorno da API

**Sucesso**: O objetivo passado como parâmetro terá suas informações alteradas de acordo com o que foi específicado pelo usuário e será retornada a mensagem de sucesso: `Sucesso ao editar Objetivo.`.

**Erro(s)**: Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando editar um objetivo da empresa que participa será retornada a mensagem de erro: `Você não tem permissão para acessar esse recurso!` Se o objetivo passado como parâmetro não for encontrado será retornada a mensagem de erro: `Registro não encontrado!`. Se acontecer algum erro ao tentar salvar o objetivo passado como parâmetro será retornada a mensagem de erro: `Erro ao editar Objetivo`. Se acontecer algum outro erro ao tentar achar o objetivo passado como parâmetro será retornada a mensagem de erro: `Erro interno no sistema`.

### Delete

#### Rota da API

DELETE -> `api/objectives/{Objective_id}`

#### Parâmetros e Suas Utilidades

Objective_id\*: o id do objetivo que será deletado

#### Retorno da API

**Sucesso**: O objetivo será deletado da empresa, não será possível acessar ou ver ele e será retornada a mensagem de sucesso: `Sucesso ao deletar Objetivo.`.

**Erro(s)**: Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando deletar um objetivo da empresa que participa será retornada a mensagem de erro: `Você não tem permissão para acessar esse recurso!` Se o objetivo passado como parâmetro não for encontrada será retornada a mensagem de erro: `Registro não encontrado!`. Se acontecer algum erro ao tentar deletar o objetivo passado como parâmetro será retornada a mensagem de erro: `Erro ao deletar Objetivo!`. Se acontecer algum outro erro ao tentar achar o objetivo passado como parâmetro será retornada a mensagem de erro: `Erro interno no sistema`.
