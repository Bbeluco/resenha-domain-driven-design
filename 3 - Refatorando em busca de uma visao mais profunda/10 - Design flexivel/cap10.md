Eh bem verdade que um software bom eh aquele que serve aos usuarios (tendo em vista que um software so eh criado se for para resolver um problema humano). Mas de nada vale o software servir ao usuario e ser ruim para os desenvolvedores trabalharem.

A ideia de um design flexivel eh que a partir de modelo pontos que podem ser alterados tenham seu desenho bem construido, ao passo que, caso a gente tente fazer algum tipo de alteracao na propria modelagem ja sera possivel ver os **efeitos colaterais**

# Interface reveladora de intencoes
Da mesma forma que se a gente usar um script que somente retorna um resultado pra gente (sem saber como determinado calculo foi feito) nao sera de grande valia, o mesmo vale para o nosso proprio codigo. Devemos alem de tornar certas regras explicitas tambem evidenciar os processos que estamos passando para atingirmos determinado resultado

_Pq eu devo criar uma interface? Nao seria mais facil so olhar a criacao da funcao?_
As interfaces (nesse contexto) existem para de forma clara ja informarem ao leitor do codigo o que sera experado daquele determinado objeto realizar. Nos entao nao precisamos da necessidade de ler determinada funcao, apenas observar a interface de um objeto ja nos dara ideias de como ele deve se comportar na teoria.

Quanto menos carga cognitiva o dev tiver ao analisar seu codigo melhor sera seu desempenho em resolver problemas do dominio.

**Se o desenvolvedor tem que considerar a implementacao de um componente para utiliza-lo, o valor do encapsulamento eh perdido**

# Contornos de dominios
Basicamente, "contornos de dominios" eh um nome bonito para descrever a seguinte situacao. Modelamos o software de uma forma ABC, e notamos que se a gente mover B pra outro lugar ele ficara melhor, mas como isso pode acabar quebrando a aplicacao vamos criar uma **gambiarra** pra fazer isso.

Na visao do autor, uma divisao ideal de dominio eh aquele que no maximo suas refatoracoes do modelo nao vao impactar a disposicao de itens internos na logica (eh como se a gente criasse coisa nova do que ja existe, e nao trocando as coisas de lugar. Sempre que trocar de lugar estamos fazendo _contorno de dominio_).

# Classes autonomas
Quanto menos interdependencia uma classe tiver, mais simples de entender ela. Essa logica deve ser buscada em cada uma das classes do projeto. Obvio que haverao casos onde alcancar isso nao sera possivel, mas eh fundamental que o dev pelo menos tente, restando assim apenas dependencias essenciais.