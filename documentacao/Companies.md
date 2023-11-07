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
