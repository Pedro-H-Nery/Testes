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
