Em suma, existem 2 niveis de refatoracoes.

Microrefatoracoes = Sao aquelas refatoracoes que fazemos a nivel de codigo, seu intuito eh deixar o codigo mais legivel, performatico, simples, etc. As alteracoes que fazemos aqui nao mudam em nada como a funcionalidade trabalha.

Refatoracoes de dominio = Essas refatoracoes sao mais complexas, elas nao ocorrem do dia pra uma noite, exige-se esforco dos arquitetos e conhecedores do dominio envolvidos. Essa refatoracao vem com o intuito de adicionar / modificar como determinada modelagem foi criada.

O autor tenta transmitir a ideia de que quanto mais vezes a gente refatorar o codigo mais ele vai ser facil de refatorar. Funciona mais ou menos assim:

Imagine que toda hora precisamos alterar o banco de dados, logo, ao inves da gente refatorar vamos deixar essa parte do sistema o mais desacoplado possivel e o mais "plugavel" possivel, assim, sempre que a gente quiser trocar poucos pontos se moverao. Em contrapartida, tudo que passa por poucas refatoracoes se mantem solido e rigido