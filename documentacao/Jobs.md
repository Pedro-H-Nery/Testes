## Jobs

### Index

#### Rota da API

GET -> `api/jobs`
GET -> `api/jobs?list_all=basic`

#### Parâmetros e Suas Utilidades

Modo de retorno das informações: Para receber um array com todas as funções da empresa do usuário onde o id da função é a chave e o nome da função é o valor é possível definir na query o parametro `list_all` como `basic`.

#### Retorno da API

**Sucesso**: Retorna uma lista com as informações de todas as funções da empresa.

**Erro(s)**: Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando ver as funções da empresa que participa será retornada a mensagem de erro: `Você não tem permissão para acessar este recurso.`

### Add

#### Rota da API

POST -> `api/jobs`

#### Parâmetros e Suas Utilidades

Sem parâmetros

#### Retorno da API

**Sucesso**: Será criada uma nova função com as informações específicadas pelo usuário e será retornada a mensagem de sucesso: `Sucesso ao adicionar Função!`.

**Erro(s)**: Se o usuário não tiver um nível de permissão igual ou superior Gestor será retornada a mensagem de erro: `Você não tem permissão para acessar este recurso.`. Se acontecer algum erro ao tentar salvar a função será retornada a mensagem de erro: `Erro ao adicionar Função.`.

### Edit

#### Rota da API

POST -> `api/jobs/{Job_id}`

#### Parâmetros e Suas Utilidades

Job_id\*: o id da função que terá suas informações alteradas

#### Retorno da API

**Sucesso**: A função passada como parâmetro terá suas informações alteradas de acordo com o que foi específicado pelo usuário e será retornada a mensagem de sucesso: `Sucesso ao editar Função.`.

**Erro(s)**: Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando editar uma função da empresa que participa será retornada a mensagem de erro: `Você não tem permissão para acessar esse recurso!` Se a função passada como parâmetro não for encontrada será retornada a mensagem de erro: `Registro não encontrado!`. Se acontecer algum erro ao tentar salvar a função passada como parâmetro será retornada a mensagem de erro: `Erro ao editar Função`. Se acontecer algum outro erro ao tentar achar a função passada como parâmetro será retornada a mensagem de erro: `Erro interno no sistema`.

### Delete

#### Rota da API

DELETE -> `api/jobs/{Job_id}`

#### Parâmetros e Suas Utilidades

Job_id\*: o id da função que será deletada

#### Retorno da API

**Sucesso**: A função será deletada da empresa, não será possível acessar ou ver ela e será retornada a mensagem de sucesso: `Sucesso ao deletar Função.`.

**Erro(s)**: Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando deletar uma função da empresa que participa será retornada a mensagem de erro: `Você não tem permissão para acessar esse recurso!` Se a função passada como parâmetro não for encontrada será retornada a mensagem de erro: `Registro não encontrado!`. Se acontecer algum erro ao tentar deletar a função passada como parâmetro será retornada a mensagem de erro: `Erro ao deletar Função!`. Se acontecer algum outro erro ao tentar achar a função passada como parâmetro será retornada a mensagem de erro: `Erro interno no sistema`.
