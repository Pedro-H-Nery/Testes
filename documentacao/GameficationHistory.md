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
