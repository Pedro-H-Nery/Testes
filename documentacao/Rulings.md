## Rulings

### Index

#### Rota da API

GET -> `api/rulings`
GET -> `api/rulings?list_all=basic`

#### Parâmetros e Suas Utilidades

Modo de retorno das informações: Para receber um array com todas as pautas da empresa do usuário onde o id da pauta é a chave e o nome da pauta é o valor é possível definir na query o parametro `list_all` como `basic`.

#### Retorno da API

**Sucesso**: Retorna uma lista com as informações de todas as pautas da empresa.

**Erro(s)**: Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando ver as pautas da empresa que participa será retornada a mensagem de erro: `Você não tem permissão para acessar este recurso.`

### Add

#### Rota da API

POST -> `api/rulings`

#### Parâmetros e Suas Utilidades

Sem parâmetros

#### Retorno da API

**Sucesso**: Será criada uma nova pauta com as informações específicadas pelo usuário e será retornada a mensagem de sucesso: `Sucesso ao adicionar Pauta!`.

**Erro(s)**: Se o usuário não tiver um nível de permissão igual ou superior Gestor será retornada a mensagem de erro: `Você não tem permissão para acessar este recurso.`. Se acontecer algum erro ao tentar salvar a pauta será retornada a mensagem de erro: `Erro ao adicionar Pauta.`.

### Edit

#### Rota da API

POST -> `api/rulings/{Ruling_id}`

#### Parâmetros e Suas Utilidades

Ruling_id\*: o id da pauta que terá suas informações alteradas

#### Retorno da API

**Sucesso**: A pauta passada como parâmetro terá suas informações alteradas de acordo com o que foi específicado pelo usuário e será retornada a mensagem de sucesso: `Sucesso ao editar Pauta.`.

**Erro(s)**: Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando editar uma pauta da empresa que participa será retornada a mensagem de erro: `Você não tem permissão para acessar esse recurso!` Se a pauta passada como parâmetro não for encontrada será retornada a mensagem de erro: `Registro não encontrado!`. Se acontecer algum erro ao tentar salvar a pauta passada como parâmetro será retornada a mensagem de erro: `Erro ao editar Pauta`. Se acontecer algum outro erro ao tentar achar a pauta passada como parâmetro será retornada a mensagem de erro: `Erro interno no sistema`.

### Delete

#### Rota da API

DELETE -> `api/rulings/{Ruling_id}`

#### Parâmetros e Suas Utilidades

Ruling_id\*: o id da pauta que será deletada

#### Retorno da API

**Sucesso**: A pauta será deletada da empresa, não será possível acessar ou ver ela e será retornada a mensagem de sucesso: `Sucesso ao deletar Pauta.`.

**Erro(s)**: Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando deletar uma pauta da empresa que participa será retornada a mensagem de erro: `Você não tem permissão para acessar esse recurso!` Se a pauta passada como parâmetro não for encontrada será retornada a mensagem de erro: `Registro não encontrado!`. Se acontecer algum erro ao tentar deletar a pauta passada como parâmetro será retornada a mensagem de erro: `Erro ao deletar Pauta!`. Se acontecer algum outro erro ao tentar achar a pauta passada como parâmetro será retornada a mensagem de erro: `Erro interno no sistema`.
