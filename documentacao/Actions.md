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
