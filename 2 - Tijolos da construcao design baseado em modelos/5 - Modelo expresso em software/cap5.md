O autor inicia o capitulo reforcando a ideia que a modelagem e implementacao sao duas coisas diferentes (e que ambas possui seu grau de complexidade para entrarem em sincronismo).

Em linhas gerais existem 3 padroes de elementos para um **modelo**, sao eles:

- Servico
- Entidade
- Objeto de valor

O autor considera a questao de servicos como sendo a logica que o codigo deve executar, enquanto a entidade guardaria o estado daquele objeto atual

### Associacoes
Existe uma regra pregada pelo autor que eh a seguinte:

_Sempre que eu tiver ligacoes entre objetos no meu diagrama, necessariamente no software eu precisarei dessas ligacoes tambem_

Quando partimos desse pressuposto entendemos que quanto mais simples e mais objetiva fora as associacoes na nossa modelagem mais simples e objetivo ficara nosso codigo tambem.

# Entidades (Objetos de Referencia)
O conceito fundamental de ENTIDADES eh uma continuidade abstrata que percorre um ciclo de vida e passa por varias formas.

Entidades nada mais sao que identificacoes de objetos.

Por mais que _entidades_ inicialmente seja definida pelo autor pelas frases que escrevi acima, o que da a entender na verdade eh que: _Entidades sao objetos unicos e identificaveis no sistema_

Imagine um estadio de futebol, la tem as cadeiras da arquibancada, cada cadeira eh uma ENTIDADE do meu sistema (ja que cada cadeira eh numerada e tem suas identificacoes). As cadeiras possuem mais do que simplesmente numeracao, elas possuem posicao, suporte ou nao a pessoas deficientes, etc. O que torna uma cadeira uma **entidade** do sistema eh a capacidade que demos a ela de a localizar de forma unica atraves do **identificador**.

Importante ressaltar que quando falamos de _identificador_ estamos nos referindo no ambito inteiro do sistema, eh como se a gente tivesse 2 bancos de dados e usasse apenas um UUID para os 2 bancos. A ideia eh que esse ID seja rastreavel por toda a aplicacao.

Outro ponto sobre identificadores eh que muito cuidado precisa ser tomado ao escolher o que sera usado como ID. Tudo sempre eh um trade-off, por exemplo:

Usar telefone como ID = Mais facil sincronizar os sistemas, risco do numero de telefone ser passado pra outra pessoa
Usar UUID = otimo para deixar exclusivo mas dificil de sincronizar
Usar nome pessoal = a pessoa pode trocar de nove (improvavel mas eh um caso)

# Objetos de valor
Sao objetos que descrevem coisas, essas "coisas" descritas geralmente sao mutaveis e irrastreaveis (o que faz com que seja bem explicita a separacacao de _Objetos de valor_ e _Entidades_). Eh correto afirmar tambem o seguinte: **objetos de valor sao valores que adiciono no sistema para enriquecer as entidades**.

Objetos de valor sao basicamente atributos (pra entender essa frase eh essencial pensar igual em linguagens orientadas a objetos onde temos instancias, atributos de instancias, etc).

Para evitar mudancas inesperadas no sistema todos os objetos de valor devem ser imutaveis. Vamos imaginar o seguinte cenario

Eu moro com meus pais na mesma casa que eles, logo, dividimos o mesmo **endereco**
Para otimizar o sistema, cada ENTIDADE pessoa que eu crio no meu sistema eu reaproveito o **endereco** caso morem no mesmo local.
1 ano se passa e eu saio da casa dos meus pais.
Se o objeto for _mutavel_ significa que ao atualizar o sistema sem querer atualizo o **endereco** dos meus pais tambem (o que esta errado, so eu me mudei de casa, eles continuam no mesmo lugar)

Obvio que nada esta escrito em pedra e podemos sim ter objetos mutaveis, mas aqui sempre deve se tomar cuidado pois muitos side-effects e perdas de performance podem acontecer, cada caso eh um caso e precisa ser analisado com cuidado

# Servicos
Servicos tratam muito mais de **acoes** do que **informacoes**. Sao basicamente estruturas criadas para realizar operacoes dentro de um sistema (veja como exemplo as classes de _Services_, constantemente encontradas em arquiteturas em camadas, um exemplo famoso: MVC).

Ja que nossos servicos realizarao operacoes, eh de bom tom criar o nome dessas operacoes com os mesmos nomes utilizados na _linguagem onipresente_

Em linhas gerais para saber se voce dividiu bem uma parte do sistema em "servicos" ele deve possuir as seguintes caracteristicas:

1. Nao ter estado definido
2. Realiza operacoes esperadas por outras partes do software (a existencia dele eh necessaria pois o software precisa resolver o problema XPTO)
3. Ele nao pode ser substituido por "Objetos de valor" nem "Entidades"

Dado a granularidade das informacoes podemos tambem dividir o sistema na ideia de **modulos**

## Modulos
Aqui buscamos 2 coisas:
- Alta coesao (os modulos sao fazem sentido entre si)
- Baixo acoplamento (um modulo nao depende do outro pra sobrevier)

A ideia de autor para modulo eh que **modulos sao um veiculo de comunicacao**. Os desenvolvedores que lerem seu projeto ao se depararem com modulos devem entender a modelagem que esta por tras daquele software. Imagine modulos como sendo pecinhas de um quebra-cabeca que se encaixam, 1 modulo pode ter N classes dentro dele, o importante na hora de modularizar o projeto eh ter ideia que voce esta criando uma ferramenta que sera usada por alguem mais tarde.

Nesse ponto de vista a ideia de modulo parece se assimilar um pouco a ideia de pacote que temos em arquiteturas do modelo _microkernel_, citadas no livro _Fundamentos da Arquitetura de Software_

Assim como tudo no sistema, os modulos tambem nao escapam de seguir a ideia da _linguagem onipresente_

Um caso curioso (porem esperado pelo livro) eh que ele defende a arquitetura em camadas porem nao defende que ela seja de forma tecnica e sim em forma de dominio. Na visao do autor quando separamos estritamente em forma tecnica tendemos a perder a coesao de codigo (ja que cada parte que potencialmente estaria junta esta muito longe fisicamente falando) e tambem aumentar muito o acoplamento (isso pq a granularidade seria maior entao pra compensar essa quebra precisariamos puxar a informacao de outro pacote/modulo)

### Paradigmas de modelagem
Nessa etapa o autor argumenta que linguagens baseadas em orientacoes a objetos sobreviveram ao teste do tempo pois eh natural das pessoas se comunicarem usando temas da orientacao a objetos. Como eh quase uma linguagem natural (e as representacoes de diagramas sao faceis de entender), linguagens orientadas a objetos sobreviveram ao teste do tempo.

_Entao quer dizer que so POO esta correto?_
Claro que nao, existem problemas da area da programacao que POO eh horrivel para resolver e solucoes melhores ja foram criadas.
O problema em tentar abordar outros paradigmas eh a questao da curva de aprendizagem dos profissionais da equipe. No inicio dos anos 90 POO estava comecando a nascer, entao muitas coisas desse tipo de paradigma nao estavam bem desenvolvidas. Eventualmente POO sera substituida por algo que hoje esta em processo embrionario tambem, e assim o ciclo de evolucao no mundo da TI vai se perpetuando.