## Sectors

### Index

#### Rota da API

GET -> `api/sectors`
GET -> `api/sectors?list_all=basic`

#### Parâmetros e Suas Utilidades

Modo de retorno das informações: Para receber um array com todos os setores da empresa do usuário onde o id do setor é a chave e o nome do setor é o valor é possível definir na query o parametro `list_all` como `basic`.

#### Retorno da API

**Sucesso**: Retorna uma lista com as informações de todos os setores da empresa.

**Erro(s)**: Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando ver os setores da empresa que participa será retornada a mensagem de erro: `Você não tem permissão para acessar este recurso.`

### Add

#### Rota da API

POST -> `api/sectors`

#### Parâmetros e Suas Utilidades

Sem parâmetros

#### Retorno da API

**Sucesso**: Será criado um novo setor com as informações específicadas pelo usuário e será retornada a mensagem de sucesso: `Sucesso ao adicionar Setor!`.

**Erro(s)**: Se o usuário não tiver nível de permissão igual ou superior a Gestor será retornada a mensagem de erro: `Você não tem permissão para acessar este recurso.`. Se o setor receber chamado mas não for específicado o prazo padrão para resposta do chamado será retornada a mensagem de erro: `Prazo padrão para resposta do chamado em dias é obrigatório quando o setor recebe chamado.`. Se acontecer algum erro ao tentar salvar o setor será retornada a mensagem de erro: `Erro ao adicionar Setor.`.

### Edit

#### Rota da API

POST -> `api/sectors/{Sector_id}`

#### Parâmetros e Suas Utilidades

Sector_id\*: o id do setor que terá suas informações alteradas

#### Retorno da API

**Sucesso**: O setor passado como parâmetro terá suas informações alteradas de acordo com o que foi específicado pelo usuário e será retornada a mensagem de sucesso: `Sucesso ao editar Setor.`.

**Erro(s)**: Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando editar um setor da empresa que participa será retornada a mensagem de erro: `Você não tem permissão para acessar esse recurso!` Se o setor receber chamado mas não for específicado o prazo padrão para resposta do chamado será retornada a mensagem de erro: `Prazo padrão para resposta do chamado em dias é obrigatório quando o setor recebe chamado.`. Se o setor passado como parâmetro não for encontrado será retornada a mensagem de erro: `Registro não encontrado!`. Se acontecer algum erro ao tentar salvar o setor passado como parâmetro será retornada a mensagem de erro: `Erro ao editar Setor`. Se acontecer algum outro erro ao tentar achar o setor passado como parâmetro será retornada a mensagem de erro: `Erro interno no sistema`.

### Delete

#### Rota da API

DELETE -> `api/sectors/{Sector_id}`

#### Parâmetros e Suas Utilidades

Sector_id\*: o id do setor que será deletado

#### Retorno da API

**Sucesso**: O setor será deletado da empresa, não será possível acessar ou ver ele e será retornada a mensagem de sucesso: `Sucesso ao deletar Setor.`.

**Erro(s)**: Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando deletar um setor da empresa que participa será retornada a mensagem de erro: `Você não tem permissão para acessar esse recurso!` Se o setor passado como parâmetro não for encontrado será retornada a mensagem de erro: `Registro não encontrado!`. Se acontecer algum erro ao tentar deletar o setor passado como parâmetro será retornada a mensagem de erro: `Erro ao deletar Setor!`. Se acontecer algum outro erro ao tentar achar o setor passado como parâmetro será retornada a mensagem de erro: `Erro interno no sistema`.
