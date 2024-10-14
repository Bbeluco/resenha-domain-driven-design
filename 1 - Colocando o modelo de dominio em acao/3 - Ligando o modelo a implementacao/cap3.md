# Model Driven design
Apenas criar um dominio sem que este tenha sido devidamente modelado acarreta em apenas mais complexidade, nao eh possivel enxergar a verdadeira forma daquele determinado dominio pois sua complexidade o mascarara.

Tendo em vista isso inicialmente criaram o **modelo de analise** (basicamente funciona assim: todos entendem o que precisa ser feito, quando chegar a hora de codificar os devs criam um projeto que so tem como objetivo fazer funcoes sem olhar ao redor, isso faz com que o codigo nao seja bem aproveitado).

O autor entende 2 coisas:

1. Um codigo com modelagem fraca nada mais eh que instrucoes para maquina que nao se explicam muito bem
2. Analise e design sao antagonicos entre si (Design complexo = pouco tempo de vida de design / Pouco analise = codigo pouquissimo explicado)

A ideia de se criar um _design dirigido ao modelo_ nasce justamente pra acabar com a diferenca entre essas 2 partes citadas pelo autor

**O design do software deve seguir literalmente o que o dominio descreve**
**O dominio deve ser o mais entendivel possivel do ponto de vista do software**