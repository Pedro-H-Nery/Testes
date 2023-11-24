## Gamefication Points

### 1. Como funciona?

Se a empresa possui gameficação e está com uma rodada ativa é possível que os usuários ganhem pontos dependendo das atividades que fazem no sistema.

### 2. Quais as atividades que geram pontos?

|            Atividade             | Pontuação Padrão |
| :------------------------------: | :--------------: |
|          Adicionar Ação          |        1         |
|    Completar Rotina Produtiva    |        3         |
|      Completar Treinamento       |        5         |
|      Concluir Ação Atrasada      |        3         |
|    Concluir Ação em Andamento    |        5         |
|   Concluir Chamado sem Solução   |        3         |
|        Concluir Checklist        |        2         |
|       Concluir Formulário        |        2         |
|          Criar Chamado           |        1         |
|         Criar Checklist          |        1         |
|        Criar Compromisso         |        2         |
|  Criar Formação Por Vídeo Aula   |        5         |
|         Criar Formulário         |        1         |
|          Criar Problema          |        1         |
|          Criar Projeto           |        1         |
|          Criar Reunião           |        1         |
|        Criar uma Formação        |        1         |
|  Estar presente em uma Formação  |        4         |
|  Estar presente em uma Reunião   |        3         |
| Fazer Metade da Rotina Produtiva |        1         |
|       Fazer um Agendamento       |        1         |
|         Resolver Chamado         |        7         |

OBS: O número máximo de vezes padrão que uma atividade pode gerar pontos por dia é 5.

Os valores de pontuação que cada atividade gera e o número de vezes máximo que elas geram pontos por dia podem ser alterados em `Gerenciar Pontos` do módulo de `Gameficação`.

É possível que alguma das atividade acima não gere pontos porque ela foi deletada ou então a quantidade de pontos que ela gera ou a quantidade máxima de vezes que ela gera pontos por dia foi zerado.

Os pontos vão ser dados para o responsável ou para o dono da atividade e não para quem concluiu ela. Ex: Se um usuário X concluir a ação do usuário Y então os pontos serão entregues para o usuário Y.

### 3. Como saber se uma atividade gerou pontos?

Quando uma atividade for feita e se ela puder gerar pontos então no campo `message` do retorno da api se tornará um array com os seguintes campos:

`message`: Mensagem de sucesso padrão da atividade;

`points_message`: Mensagem de sucesso com a quantidade de pontos que a atividade gerou e o total de pontos;

`points`: Pontos que a atividade gerou;

`total`: Pontos totais do usuário na rodada atual;

`error`: Tipo de erro que ocorreu.

### 4. Quais são os erros possíveis?

1.  `Unregistered Activity` -> A atividade não está registrada para gerar pontos.
2.  `No Rounds` -> A empresa não possui uma rodada ativa.
3.  `Max Times` -> O usuário já fez o máximo de vezes que a atividade gera pontos e por isso receberá 0 pontos pela atividade.
