## Managarment Tools

### Index

#### Rota da API

GET -> `api/managerment_tools`
GET -> `api/managerment_tools?list_all=basic`

#### Parâmetros e Suas Utilidades

Modo de retorno das informações: Para receber um array com todas as ferramentas de gestão da empresa do usuário onde o id da ferramenta de gestão é a chave e o nome da ferramenta de gestão é o valor é possível definir na query o parametro `list_all` como `basic`.

#### Retorno da API

**Sucesso**: Retorna uma lista com as informações de todas as ferramentas de gestão da empresa.

**Erro(s)**: Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando ver as ferramentas de gestão da empresa que participa será retornada a mensagem de erro: `Você não tem permissão para acessar este recurso.`

### Add

#### Rota da API

POST -> `api/managerment_tools`

#### Parâmetros e Suas Utilidades

Sem parâmetros

#### Retorno da API

**Sucesso**: Será criada uma nova ferramenta de gestão com as informações específicadas pelo usuário e será retornada a mensagem de sucesso: `Sucesso ao adicionar Ferramenta de Gestão!`.

**Erro(s)**: Se o usuário não tiver um nível de permissão igual ou superior Gestor será retornada a mensagem de erro: `Você não tem permissão para acessar este recurso.`. Se acontecer algum erro ao tentar salvar a ferramenta de gestão será retornada a mensagem de erro: `Erro ao adicionar Ferramenta de Gestão.`.

### Edit

#### Rota da API

POST -> `api/managerment_tools/{Managerment_Tool_id}`

#### Parâmetros e Suas Utilidades

Managerment_Tool_id\*: o id da ferramenta de gestão que terá suas informações alteradas

#### Retorno da API

**Sucesso**: A ferramenta de gestão passada como parâmetro terá suas informações alteradas de acordo com o que foi específicado pelo usuário e será retornada a mensagem de sucesso: `Sucesso ao editar Ferramenta de Gestão.`.

**Erro(s)**: Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando editar uma ferramenta de gestão da empresa que participa será retornada a mensagem de erro: `Você não tem permissão para acessar esse recurso!` Se a ferramenta de gestão passada como parâmetro não for encontrada será retornada a mensagem de erro: `Registro não encontrado!`. Se acontecer algum erro ao tentar salvar a ferramenta de gestão passada como parâmetro será retornada a mensagem de erro: `Erro ao editar Ferramenta de Gestão`. Se acontecer algum outro erro ao tentar achar a ferramenta de gestão passada como parâmetro será retornada a mensagem de erro: `Erro interno no sistema`.

### Delete

#### Rota da API

DELETE -> `api/managerment_tools/{Managerment_Tool_id}`

#### Parâmetros e Suas Utilidades

Managerment_Tool_id\*: o id da ferramenta de gestão que será deletada

#### Retorno da API

**Sucesso**: A ferramenta de gestão será deletada da empresa, não será possível acessar ou ver ela e será retornada a mensagem de sucesso: `Sucesso ao deletar Ferramenta de Gestão.`.

**Erro(s)**: Se o usuário não for Master ou então não for um usuário de nível de permissão igual ou superior a Gestor tentando deletar uma ferramenta de gestão da empresa que participa será retornada a mensagem de erro: `Você não tem permissão para acessar esse recurso!` Se a ferramenta de gestão passada como parâmetro não for encontrada será retornada a mensagem de erro: `Registro não encontrado!`. Se acontecer algum erro ao tentar deletar a ferramenta de gestão passada como parâmetro será retornada a mensagem de erro: `Erro ao deletar Ferramenta de Gestão!`. Se acontecer algum outro erro ao tentar achar a ferramenta de gestão passada como parâmetro será retornada a mensagem de erro: `Erro interno no sistema`.
