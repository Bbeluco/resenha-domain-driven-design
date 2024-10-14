Saber se comunicar com outros membros da equipe (seja tecnica ou nao tecnica) eh tao importante quanto saber codar bem. Pra falar a verdade, o que se entende da fala do autor eh que "codar bem" significa **conseguir compilar o modelo de determinado dominio de forma assertiva**.

Eh de suma importancia que todos da equipe falem a mesma lingua. Durante o desenvolvimento de software **nao deve haver espacos para multiplas interpretacoes** pois se isso acontecer tanto o software final devera ser refatorado quanto a entrega tende a atrasar.

Um ponto interessante levantado pelo autor eh que devemos tomar cuidado sobre _quem_ entende o que eh falado no time de analistas de modelagem, isso pq se so uma pessoa entender o que eles falam essa sera o unico ponto de interseccao entre as equipes, o que eventualmente gerara gargalos e a entrega do projeto sera impactada (ou a pessoa ficara sobrecarregada)

Na visao do autor temos entao o seguinte problema:

A equipe X usa um jeito de fala e a equipe Y usa outro.

_Qual o nosso objetivo_
Sincronizar a fala da equipe X (que pode ser algo mais tecnico) com a equipe Y (que pode ser algo menos tecnico)

A ideia do autor para isso eh criar o que ele chama de **linguagem onipresente** (significa que essa linguagem sera de uso comum na organizacao, quando todos comecarem a se comunicar na mesma lingua todos eles vao se entender mais facilmente). Modelos criados na organizacao devem seguir a linguagem onipresente, se por acaso alguma palavra da linguagem for trocada o modelo deve se atualizar de acordo com essa troca.

**A linguagem onipresente deve ser a interseccao de termos utilizados entre equipe tecnica e equipe nao tecnica**. Caso precise poir algum motivo entrar no detalhe ai sim o representante de cada uma das areas pode entrar nesse tema de forma breve

# Modelando em voz alta
Modelagem nada mais eh do que pegar o seu entendimento sobre determinado assunto e passar ele para uma representacao (seja visual, escrita, falada etc).

O autor parte do seguinte principio: **Se** utilizamos linguagem (portugues, ingles, etc) no dia a dia para nos comunicarmos **entao** criar a _linguagem onipresente_ vai nos ajudar a resolver o dominio de forma mais assertiva

A linguagem ela eh viva (seja dentro de uma empresa ou o portugues falado mesmo), e como toda linguagem viva ela sofre alteracoes em razao do tempo. Outro ponto tambem eh o modo de falar, se voce for aprender espanhol no comeco sua fala sera muito pobre e muito fora da sua zona de conforto para se comunicar, porem, se voce investir tempo nisso tera uma fala mais fluida e direta. Essa eh a ideia de praticar o uso da _linguagem onipresente_, vai chegar uma hora que voce vai ter praticado tanto que sera "direto e reto" na sua fala e todos entenderao

# Documentos e diagramas
**Modelagem nao se resume a diagrama**, codigos podem tambem significar diagramas. Em suma inserir elementos visuais pode facilitar a equalizar o entendimento de todos os envolvidos no projeto

# Documentos de design
Os documentos acabam sofrendo do mesmo mal de comentarios em codigo, **eles ficam defazados muito rapidamente**. Seja pq a fala da empresa evoluiu (e antes o que era chamado de A agora eh chamado de B), seja pq o fluxo do codigo mudou (e agora o documento deveria ter sido atualizado e nao foi), etc.

Eh importante escrever um documento que pense nesse tipo de detalhe. Segundo o autor, no Extreme Programming eh recomendado nao utilizar nenhum documento para se referir ao codigo por conta disso.

Honestamente nao acho que precisamos ser tao radicais assim (ao ponto de nao ter documento nenhum pra explicar o codigo), mas precisamos garantir que nosso documento vai sobreviver (entenda nesse caso, fazer sentido) o maximo de tempo possivel