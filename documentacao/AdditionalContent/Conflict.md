## Conflict

### 1. Como funciona?

Acontecerá um conflito se o usuário estiver tentando cadastrar ou editar uma reunião ou compromisso em que:

1. O usuário já possui uma reunião ou compromisso já cadastrado entre a data de início e de fim;
2. A data de início está entre a data de inicío e de fim de outra reunião ou compromisso já cadastrado;
3. A data de fim está entre a data de início e de fim de outro reunião ou compromisso já cadastrado.

### 2. Como saber se um conflito aconteceu?

Quando um evento ou reunião for tentar ser adicionada/editada mas aconteceu um conflito então os seguintes campos estarão preenchidos:

`conflict`: `true`;

`conflicted_users_text`: `"<strong>{Nome do usuário}, \"{Nome do Usuário}\" são os usuários que possuem conflito de horário com {o evento/a reunião} que você quer agendar</strong><br>Se você realmente deseja cadastar {esse evento/ essa reunião} clique no botão novamente."`;

`conflicted_init_date`: Data de início que gerou conflito;

`conflicted_end_date`: Data de fim que gerou conflito;

### 3. Como resolver um conflito?

Para resolver um conflito o usuário precisa mudar a data de início e/ou de fim até que elas não gerem conflito com alguma outra reunião ou compromisso que o usuário já possui ou então o usuário mesmo sabendo do conflito decide ignorar o conflito e cadastrar mesmo assim a reunião ou compromisso conflitante. Para que ele posso ignorar o conflito ele precisar tentar cadastrar/editar novamente a reunião ou compromisso com a mesma data de início e de fim que gerou o conflito, ou seja, o atributo de data de início precisa ser igual a `conflicted_init_date` e o atributo de data de fim precisa ser igual a `conflicted_end_date`. É possível que ao tentar mudar a data de fim e a data de início para uma nova data essa nova data também possa gerar conflito.
