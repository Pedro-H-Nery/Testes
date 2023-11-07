## Units

### Index

#### Rota da API

GET -> `api/units`
GET -> `api/units?list_all=basic`

#### Parâmetros e Suas Utilidades

Modo de retorno das informações: Para receber um array com todas as unidades da empresa do usuário onde o id da unidade é a chave e o nome da unidade é o valor é possível definir na query o parametro `list_all` como `basic`.

#### Retorno da API

**Sucesso**: Retorna uma lista com as informações de todas as unidades da empresa.

**Erro(s)**: Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando ver as unidades da empresa que participa será retornada a mensagem de erro: `Você não tem permissão para acessar este recurso.`

### Add

#### Rota da API

POST -> `api/units`

#### Parâmetros e Suas Utilidades

Sem parâmetros

#### Retorno da API

**Sucesso**: Será criada uma nova unidade com as informações específicadas pelo usuário e será retornada a mensagem de sucesso: `Sucesso ao adicionar Unidade!`.

**Erro(s)**: Se o usuário não tiver um nível de permissão igual ou superior Gestor será retornada a mensagem de erro: `Você não tem permissão para acessar este recurso.`. Se acontecer algum erro ao tentar salvar a unidade será retornada a mensagem de erro: `Erro ao adicionar Unidade.`.

### Edit

#### Rota da API

POST -> `api/units/{Unit_id}`

#### Parâmetros e Suas Utilidades

Unit_id\*: o id da unidade que terá suas informações alteradas

#### Retorno da API

**Sucesso**: A unidade passada como parâmetro terá suas informações alteradas de acordo com o que foi específicado pelo usuário e será retornada a mensagem de sucesso: `Sucesso ao editar Unidade.`.

**Erro(s)**: Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando editar uma unidade da empresa que participa será retornada a mensagem de erro: `Você não tem permissão para acessar esse recurso!` Se a unidade passada como parâmetro não for encontrada será retornada a mensagem de erro: `Registro não encontrado!`. Se acontecer algum erro ao tentar salvar a unidade passada como parâmetro será retornada a mensagem de erro: `Erro ao editar Unidade`. Se acontecer algum outro erro ao tentar achar a unidade passada como parâmetro será retornada a mensagem de erro: `Erro interno no sistema`.

### Delete

#### Rota da API

DELETE -> `api/units/{Unit_id}`

#### Parâmetros e Suas Utilidades

Unit_id\*: o id da unidade que será deletada

#### Retorno da API

**Sucesso**: A unidade será deletada da empresa, não será possível acessar ou ver ela e será retornada a mensagem de sucesso: `Sucesso ao deletar Unidade.`.

**Erro(s)**: Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando deletar uma unidade da empresa que participa será retornada a mensagem de erro: `Você não tem permissão para acessar esse recurso!` Se a unidade passada como parâmetro não for encontrada será retornada a mensagem de erro: `Registro não encontrado!`. Se acontecer algum erro ao tentar deletar a unidade passada como parâmetro será retornada a mensagem de erro: `Erro ao deletar Unidade!`. Se acontecer algum outro erro ao tentar achar a unidade passada como parâmetro será retornada a mensagem de erro: `Erro interno no sistema`.
