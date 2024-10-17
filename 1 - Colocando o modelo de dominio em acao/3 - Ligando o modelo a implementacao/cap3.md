# Model Driven design
Apenas criar um dominio sem que este tenha sido devidamente modelado acarreta em apenas mais complexidade, nao eh possivel enxergar a verdadeira forma daquele determinado dominio pois sua complexidade o mascarara.

Tendo em vista isso inicialmente criaram o **modelo de analise** (basicamente funciona assim: todos entendem o que precisa ser feito, quando chegar a hora de codificar os devs criam um projeto que so tem como objetivo fazer funcoes sem olhar ao redor, isso faz com que o codigo nao seja bem aproveitado).

O autor entende 2 coisas:

1. Um codigo com modelagem fraca nada mais eh que instrucoes para maquina que nao se explicam muito bem
2. Analise e design sao antagonicos entre si (Design complexo = pouco tempo de vida de design / Pouco analise = codigo pouquissimo explicado)

A ideia de se criar um _design dirigido ao modelo_ nasce justamente pra acabar com a diferenca entre essas 2 partes citadas pelo autor

**O design do software deve seguir literalmente o que o dominio descreve**
**O dominio deve ser o mais entendivel possivel do ponto de vista do software**

Em suma, quando dominios sao resolvidos sempre temos que levar em conta a visao que o usuario tera sobre aquele sistema (esse eh o motivo da modelagem ser um aspecto tao importante), desenvolver um sistema que passe a ideia A mas na verdade faz o B causa uma experiencia muito ruim aos olhos do usuario.

Quando temos uma separacao muito bem definida em modelagem, design e programacao, alcancamos o que chamamos de **Design dirigido por modelo**.
O livro tambem reforca a ideia que foi passada no livro _Introducao a arquitetura de Software_ que eh a seguinte: Separar o arquiteto da equipe de desenvolvimento so vai dificultar ainda mais a comunicacao da equipe e o software nao vai sair como esperado. Eh essencial para o bom funcionamento da solucao de software que acontecam 2 coisas: Proximidade do arquiteto com os devs e que os desenvolvedores entendam para que eles estao codando, **um dev que nao entende para que serve aquele dominio dificilmente vai conseguir criar um sistema coeso** 

# Paradigma das modelagens
Linguagens orientadas a objetos tem uma certa vantagem no quesito de organizacao e modelagem de codigo quando comparadas a linguagens procedurais. As linguagens procedurais _tendem_ a buscar mais a parte de como fazer o codigo A resolver o problema X (pouco importando como esse codigo sera organizado), enquanto linguagens orientadas a objetos tendem a manter uma coesao maior do pq determinadas coisas estao organizadas dessa foram. Quem esta falando isso nao sou eu e sim o autor do livro

## Design dirigido por modelos
No livro o autor da um exemplo falando em como na abordagem orientada a objetos por atingir niveis de separacao maiores (e tambem por permitir que essas separacoes sejam testadas) acaba sendo a solucao mais viavel do ponto de vista de desenvolver solucoes mais complexas