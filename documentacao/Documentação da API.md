# Documentação da API

## Company Points

### Index

#### Rota da API

GET -> `api/company-points`

#### Parâmetros e Suas Utilidades

Sem parâmetros

#### Retorno da API

**Sucesso**: Retorna uma lista com todas as atividades da empresa que geram pontos e dentro de cada atividade está os pontos que ela gera ao ser feita e o máximo de vezes que ela gera pontos por dia

**Erro(s)**:
Se o usuário não for Master ou então for Admin e da empresa será retornada a mensagem de erro: `Você não tem permissão para acessar este recurso.`

### Add

#### Rota da API

POST -> `api/company-points`

#### Parâmetros e Suas Utilidades

Sem parâmetros

#### Retorno da API

**Sucesso**: As atividades que foram escolhidas para serem adicionadas pelo usuário são salvas no sistema e vão começar a gerar pontos e será retornada a mensagem de sucesso: `As atividades tiveram suas pontuações padrões atribuidas com sucesso.`

**Erro(s)**:
Se o usuário não for Master ou então for Admin e da empresa será retornada a mensagem de erro: `Você não tem permissão para acessar este recurso.`
Se não tiver mais nenhuma atividade que seja possível adicionar a empresa será retornada a mensagem de erro: `Não existem mais atividades para atribuir uma pontuação.`.
Se acontecer algum erro ao tentar salvar as atividades será retornada a mensagem de erro: `Não foi possível atribuir pontuação as atividades. Por favor, tente novamente.`

### Edit

#### Rota da API

POST -> `api/company-points/edit/{Nome em Português da Atividade}`

#### Parâmetros e Suas Utilidades

Nome em Português da Atividade\*: nome da atividade que será editada

#### Retorno da API

**Sucesso**: A atividade que foi passada como parâmetro terá os pontos que ela gera e o máximo de vezes que ela gera pontos por dia salvas no sistema e será retornada a mensagem de sucesso: `A geração de pontos da atividade {Nome em Português da Atividade} foi editada com sucesso.`. Se os pontos que ela gera ou o máximo de vezes que ela gera pontos for 0 a atividade não vai gerar pontos e não irá aparecer no index de Comapny Points.

**Erro(s)**:
Se o usuário não for Master ou então for Admin e da empresa será retornada a mensagem de erro: `Você não tem permissão para acessar este recurso.`
Se acontecer algum erro ao tentar salvar as atividades será retornada a mensagem de erro: `A geração de pontos da atividade {Nome em Português da Atividade} não pôde ser editada. Por favor, tente novamente.`

### Delete

#### Rota da API

DELETE -> `/api/company-points/edit/{Nome em Português da Atividade}`

#### Parâmetros e Suas Utilidades

Nome em Português da Atividade\*: nome da atividade que não irá gerar pontos

#### Retorno da API

**Sucesso**: A atividade que foi passada como parâmetro não irá gerar pontos ao ser realizada, não irá aparecer no index de Comapny Points e será retornada a mensagem de sucesso: `A geração de pontos da atividade {Nome em Português da Atividade} foi removida com sucesso.`.

**Erro(s)**:
Se o usuário não for Master ou então for Admin e da empresa será retornada a mensagem de erro: `Você não tem permissão para acessar este recurso.`
Se acontecer algum erro ao tentar salvar as atividades será retornada a mensagem de erro: `A geração de pontos da atividade {Nome em Português da Atividade} não pôde ser removida. Por favor, tente novamente.`

## Gamefication History

### Index

#### Rota da API

GET -> `api/gamefication-history`
GET -> `api/gamefication-history/{User_id}`

#### Parâmetros e Suas Utilidades

User_id: Id do usuário que se deseja ver o histórico(se não for especifícado será retornado o histórico do usuário atual)

#### Retorno da API

**Sucesso**: Retorna uma lista com todas as atividades feitas pelo usuário específicado(ou o usuário atual) e também o número total de pontos que aquele usuário possui na rodada atual.

**Erro(s)**: Se o usuário estiver tentando ver o histórico de outro usuário e não for pelo menos Admin será retornada a mensagem de erro: `Você não tem permissão para acessar este recurso.`

### Best Users

#### Rota da API

GET -> `api/gamefication-history/best-users`
GET -> `api/gamefication-history/best-users/{Round_id}`

#### Parâmetros e Suas Utilidades

Round_id: Id da rodada que se deseja ver os melhores usuários(se não for especifícado será retornado os melhores usuários da rodada atual)

#### Retorno da API

**Sucesso**: Retorna o número da rodada e uma lista com os melhores usuário em ordem decrescente de pontos na rodada e cada usuário possui seu nome e os seus pontos.

**Erro(s)**: Sem retorno de erros.

## Rounds

### Index

#### Rota da API

GET -> `/api/rounds`

#### Parâmetros e Suas Utilidades

Sem parâmetros

#### Retorno da API

**Sucesso**: Retorna uma lista com as informações de todas as rodadas passadas, da rodada atual e da próxima rodada da empresa

**Erro(s)**: Se o usuário não for Master ou então for Admin e da empresa será retornada a mensagem de erro: `Você não tem permissão para acessar este recurso.`

### Edit

#### Rota da API

GET -> `/api/rounds/{Round_id}`

#### Parâmetros e Suas Utilidades

Round_id\*: Id da rodada que será editada

#### Retorno da API

**Sucesso**: A rodada que foi passada como parâmetro terá suas informações alteradas de acordo com o que foi específicado pelo usuário e será retornada a mensagem de sucesso: `Sucesso ao editar Rodada.`. Se a próxima rodada não for a que foi passada como parâmetro e ainda não teve suas informações definifas ela terá suas informações alteradas baseada na rodada salva

**Erro(s)**: Se o usuário não for Master ou então for Admin e da empresa será retornada a mensagem de erro: `Você não tem permissão para acessar este recurso.`. Se a data definida na edição da rodada já tiver alguma rodada cadastrada será retornada a mensagem de erro: `Já existe uma rodada cadastrada nessa data.`. Se acontecer algum erro ao tentar salvar a rodada será retornada a mensagem de erro: `Erro ao editar Rodada.`.

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

## Companies

### Index

#### Rota da API

GET -> `api/companies`

#### Parâmetros e Suas Utilidades

Sem parâmetros

#### Retorno da API

**Sucesso**: Retorna uma lista com as informações de todas as empresas do sistema.

**Erro(s)**: Se o usuário não tiver nível de permissão igual a Master será retornada a mensagem de erro: `Você não tem permissão para acessar este recurso.`

### Add

#### Rota da API

POST -> `api/companies`

#### Parâmetros e Suas Utilidades

Sem parâmetros

#### Retorno da API

**Sucesso**: Será criada uma nova empresa com as informações específicadas pelo usuário e será retornada a mensagem de sucesso: `A compania {Nome da empresa} foi salva.`.

**Erro(s)**: Se o usuário não tiver nível de permissão igual a Master será retornada a mensagem de erro: `Você não tem permissão para acessar este recurso.`. Se acontecer algum erro ao tentar salvar a empresa será retornada a mensagem de erro: `A compania {Nome da empresa} não pode ser salva. Por favor , tente novamente.`.

### Perfil Company

#### Rota da API

POST -> `api/companies/perfil-company/{Company_id}`

#### Parâmetros e Suas Utilidades

Company_id\*: o id da empresa que se deseja ver as informações

#### Retorno da API

**Sucesso**: Retorna as informações da empresa passada como parâmetro e um lista com os planos disponíveis.

**Erro(s)**: Se o usuário não tiver nível de permissão igual a Master será retornada a mensagem de erro: `Você não tem permissão para acessar este recurso.`.

### Perfil Edit

#### Rota da API

POST -> `api/companies/perfil-edit/{Company_id}`

#### Parâmetros e Suas Utilidades

Company_id\*: o id da empresa que se deseja editar as informações

#### Retorno da API

**Sucesso**: A empresa passada como parâmetro terá suas informações alteradas de acordo com o que foi específicado pelo usuário e será retornada a mensagem de sucesso: `Compania atualizada com sucesso!`. Se o usuário tiver selecionado `Possui Gameficação` então será criado um registro da pontuação das atividades da empresa e duas rodadas(a rodada atual e a próxima rodada) e elas poderão ser modificação no Módulo de Gameficação. Se o opção `Possui Gameficação` já estava selecionada e o usuário desativou ela então o registro de pontuação das atividades da empresa será deletado.

**Erro(s)**: Se o usuário não tiver nível de permissão igual a Master será retornada a mensagem de erro: `Você não tem permissão para acessar este recurso.`. Se acontecer algum erro ao tentar salvar a empresa será retornada a mensagem de erro: `Erro ao atualizar compania!`.

### Delete

#### Rota da API

POST -> `api/companies/perfil-edit/{Company_id}`

#### Parâmetros e Suas Utilidades

Company_id\*: o id da empresa que se deseja deletar

#### Retorno da API

**Sucesso**: A empresa será deletada do sistema, não será possível acessar ou ver ela e será retornada a mensagem de sucesso: `A compania {Nome da empresa} foi deletada.`.

**Erro(s)**: Se o usuário não tiver nível de permissão igual a Master será retornada a mensagem de erro: `Você não tem permissão para acessar este recurso.`. Se acontecer algum erro ao tentar deletar a empresa será retornada a mensagem de erro: `A compania {Nome da empresa} não pode ser deletado. Por favor, tente novamente.`.

## Users

### Index

#### Rota da API

GET -> `api/users`

#### Parâmetros e Suas Utilidades

Sem parâmetros

#### Retorno da API

**Sucesso**:

**Erro(s)**:

### Add

#### Rota da API

POST -> `api/users`

#### Parâmetros e Suas Utilidades

Sem parâmetros

#### Retorno da API

**Sucesso**:

**Erro(s)**:

### Edit

#### Rota da API

POST -> `api/users/{User_id}`

#### Parâmetros e Suas Utilidades

User_id\*: id do usuário que será editado

#### Retorno da API

**Sucesso**:

**Erro(s)**:

### Delete

#### Rota da API

DELETE -> `api/users/{User_id}`

#### Parâmetros e Suas Utilidades

User_id\*: id do usuário que será deletado

#### Retorno da API

**Sucesso**:

**Erro(s)**:

### Profile

#### Rota da API

GET -> `api/users/profile/{User_id}`

#### Parâmetros e Suas Utilidades

User_id\*: id do usuário que se deseja ver o perfil

#### Retorno da API

**Sucesso**:

**Erro(s)**:

### Profile Edit

#### Rota da API

POST -> `api/users/{User_id}`

#### Parâmetros e Suas Utilidades

User_id\*: id do usuário que terá o perfil editado

#### Retorno da API

**Sucesso**:

**Erro(s)**:

### Aderency

#### Rota da API

GET -> `api/users/aderency`

#### Parâmetros e Suas Utilidades

Sem parâmetros

#### Retorno da API

**Sucesso**:

**Erro(s)**:

### Select User

#### Rota da API

GET -> `api/users/select-users`

#### Parâmetros e Suas Utilidades

Sem parâmetros

#### Retorno da API

**Sucesso**:

**Erro(s)**:

### Aderency Details

#### Rota da API

GET -> `api/users/aderency-details/{User_id}`

#### Parâmetros e Suas Utilidades

User_id\*: id do usuário que se deseja ver os detalhes na aderência

#### Retorno da API

**Sucesso**:

**Erro(s)**:

## Events

### Index

#### Rota da API

GET -> `api/events`
GET -> `api/events/{Users_ids}`

#### Parâmetros e Suas Utilidades

Users_ids: lista com um ou mais usuários que será vista a agenda. Se não for especifícado a agenda do usuário atual será retornada

#### Retorno da API

**Sucesso**:

**Erro(s)**:

### Add

#### Rota da API

POST -> `api/events`

#### Parâmetros e Suas Utilidades

Sem parâmetros

#### Retorno da API

**Sucesso**:

**Erro(s)**:

### View

#### Rota da API

GET -> `api/events/{User_id}/{Model_type}/{Model_id}`

#### Parâmetros e Suas Utilidades

User_id\*: id do usuário que está tentando ver um ítem da agenda
Model_type\*: nome do modelo do ítem da agenda que o usuário está tentando ver(Ex: action ou holiday)
Model_id\*: id do ítem da agenda que o usuário está tentando ver

#### Retorno da API

**Sucesso**:

**Erro(s)**:

### Edit

#### Rota da API

POST -> `api/events/{Event_id}`

#### Parâmetros e Suas Utilidades

Event_id\*: id do evento que será editado

#### Retorno da API

**Sucesso**:

**Erro(s)**:

### Delete

#### Rota da API

DELETE -> `api/events/{Event_id}`

#### Parâmetros e Suas Utilidades

Event_id\*: id do evento que será deletado

#### Retorno da API

**Sucesso**:

**Erro(s)**:

## Actions

### Index

#### Rota da API

GET -> `api/actions`

#### Parâmetros e Suas Utilidades

Sem parâmetros

#### Retorno da API

**Sucesso**:

**Erro(s)**:

### Add

#### Rota da API

POST -> `api/actions`

#### Parâmetros e Suas Utilidades

Sem parâmetros

#### Retorno da API

**Sucesso**:

**Erro(s)**:

### Edit

#### Rota da API

POST -> `api/actions/{Action_id}`

#### Parâmetros e Suas Utilidades

Action_id\*: id da ação que será editada

#### Retorno da API

**Sucesso**:

**Erro(s)**:

### Complete

#### Rota da API

GET -> `api/action/complete/{Action_id}`

#### Parâmetros e Suas Utilidades

Action_id\*: Id da ação que será completada

#### Retorno da API

**Sucesso**: A ação que foi passada com parâmetro será completada e será retornada as informações da ação que foi completada e a mensagem de sucesso: `Ação concluída com sucesso!`. Se a empresa tiver ativado a gameficação então o usuário que completou a ação ganhará pontos baseado nos pontos de Completar Ação Em Andamento se a ação estava em andamento ou então em Completar Ação Atrasada se a ação estava atrasada que a empresa definiu e se for uma requisição API também será retornado uma lista contendo a mensagem de sucesso, a mensagem de pontos, os pontos que o usuário ganhou, o total de pontos do usuário e se aconteceu algum erro.

**Erro(s)**:
Erro ao salvar: `Erro ao concluir ação!`;
Erro de permissão: `Você não tem permissão para concluir essa ação!` => Usuário não é master ou então admin tentando completar ação na empresa que participa ou é um dos responsáveis pela ação.

### Delete

#### Rota da API

DELETE -> `api/actions/{Action_id}`

#### Parâmetros e Suas Utilidades

Action_id\*: id da ação que será deletada

#### Retorno da API

**Sucesso**:

**Erro(s)**:

## Schedules

### Index

#### Rota da API

GET -> `api/schedules`

#### Parâmetros e Suas Utilidades

Sem parâmetros

#### Retorno da API

**Sucesso**:

**Erro(s)**:

### Add

#### Rota da API

POST -> `api/schedules`

#### Parâmetros e Suas Utilidades

Sem parâmetros

#### Retorno da API

**Sucesso**:

**Erro(s)**:

### Edit

#### Rota da API

PUT -> `api/schedules/{Schedule_id}`

#### Parâmetros e Suas Utilidades

Schedule_id\*: id da schedule que será editada

#### Retorno da API

**Sucesso**:

**Erro(s)**:

### View

#### Rota da API

GET -> `api/schedules/{Schedule_id}`

#### Parâmetros e Suas Utilidades

Schedule_id\*: id da schedule que se deseja ver

#### Retorno da API

**Sucesso**:

**Erro(s)**:

### Meet

#### Rota da API

GET -> `api/schedules/meets/{Schedule_id}`

#### Parâmetros e Suas Utilidades

Schedule_id\*: id da schedule que será montada a reunião

#### Retorno da API

**Sucesso**:

**Erro(s)**:

### Delete

#### Rota da API

DELETE -> `api/schedules/{Schedule_id}`

#### Parâmetros e Suas Utilidades

Schedule_id\*: id da schedule que será deletada

#### Retorno da API

**Sucesso**:

**Erro(s)**:

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
