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
