A destilacao eh o processo de separar componentes misturados para extrair algo util e valioso. Basicamente vamos usar destilacao na area de DDD para encontrarmos o **dominio principal**, isso ira nos ajudar a entender melhor como o sistema funciona o que permite como consequencia refatorar com maior assertividade e tambem exemplificar melhor para outros membros da equipe como determinado modelo se comportara.

# Dominio principal
Eh basicamente o core da sua aplicacao, ela precisa ser flexivel e extremamente bem desenvolvida para que assim outros devs que entrarem no projeto consigam alterar essas partes do modelo sem precisar se preocupar em quebrar a aplicacao.

O autor defende a ideia de que os codigos que voce fizer no dominio principal devem ser **genericos**. Generico nao significa reutilizavel, ele passa mais a ideia que se voce quiser "plugar" alguma coisa nesse modelo sera simples de fazer essa atualizacao (entra muito na ideia de _microkernel architecture_)

## Declaracao da visao de dominio
Isso eh basicamente o que o sistema **tem como objetivo fazer**. Aqui nao vamos entrar no detalhe de **como** ele vai fazer isso, e sim **o que** ele ira fazer (e tambem o que nao vai fazer).