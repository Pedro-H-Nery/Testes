## Rules

### Index

#### Rota da API

GET -> `api/rules`
GET -> `api/rules?list_all=basic`

#### Parâmetros e Suas Utilidades

Modo de retorno das informações: Para receber um array com todas as regras da empresa do usuário onde o id da regra é a chave e o nome da regra é o valor é possível definir na query o parametro `list_all` como `basic`.

#### Retorno da API

**Sucesso**: Retorna uma lista com as informações de todas as regras da empresa.

**Erro(s)**: Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando ver as regras da empresa que participa será retornada a mensagem de erro: `Você não tem permissão para acessar este recurso.`

### Add

#### Rota da API

POST -> `api/rules`

#### Parâmetros e Suas Utilidades

Sem parâmetros

#### Retorno da API

**Sucesso**: Será criada uma nova regra com as informações específicadas pelo usuário e será retornada a mensagem de sucesso: `Sucesso ao adicionar Regra!`.

**Erro(s)**: Se o usuário não tiver um nível de permissão igual ou superior Gestor será retornada a mensagem de erro: `Você não tem permissão para acessar este recurso.`. Se acontecer algum erro ao tentar salvar a regra será retornada a mensagem de erro: `Erro ao adicionar Regra.`.

### Edit

#### Rota da API

POST -> `api/rules/{Rule_id}`

#### Parâmetros e Suas Utilidades

Rule_id\*: o id da regra que terá suas informações alteradas

#### Retorno da API

**Sucesso**: A regra passada como parâmetro terá suas informações alteradas de acordo com o que foi específicado pelo usuário e será retornada a mensagem de sucesso: `Sucesso ao editar Regra.`.

**Erro(s)**: Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando editar uma regra da empresa que participa será retornada a mensagem de erro: `Você não tem permissão para acessar esse recurso!` Se a regra passada como parâmetro não for encontrada será retornada a mensagem de erro: `Registro não encontrado!`. Se acontecer algum erro ao tentar salvar a regra passada como parâmetro será retornada a mensagem de erro: `Erro ao editar Regra`. Se acontecer algum outro erro ao tentar achar a regra passada como parâmetro será retornada a mensagem de erro: `Erro interno no sistema`.

### Delete

#### Rota da API

DELETE -> `api/rules/{Rule_id}`

#### Parâmetros e Suas Utilidades

Rule_id\*: o id da regra que será deletada

#### Retorno da API

**Sucesso**: A regra será deletada da empresa, não será possível acessar ou ver ela e será retornada a mensagem de sucesso: `Sucesso ao deletar Regra.`.

**Erro(s)**: Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando deletar uma regra da empresa que participa será retornada a mensagem de erro: `Você não tem permissão para acessar esse recurso!` Se a regra passada como parâmetro não for encontrada será retornada a mensagem de erro: `Registro não encontrado!`. Se acontecer algum erro ao tentar deletar a regra passada como parâmetro será retornada a mensagem de erro: `Erro ao deletar Regra!`. Se acontecer algum outro erro ao tentar achar a regra passada como parâmetro será retornada a mensagem de erro: `Erro interno no sistema`.
