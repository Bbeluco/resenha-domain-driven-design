Para entendermos essas diferencas primeiro precisamos definir o que eh um padrao. Segundo o livro _Design Patters_ um padrao eh: **descricoes de objetos e classes de comunicacao que sao personalizados para resolverem determinado problema de design em determinado contexto**

Basicamente vamos ter 2 tipos de padrao:

Padrao de design: Este tende a ser uma padrao **tecnico**, diz respeito a como tecnicamente determinada coisa sera feita e sera padronizada

Padrao de dominio: Este eh um padrao em como um sistema sera estruturado

# Estrategia
A ideia eh basicamente seguir a mesma logica do padrao **STRATEGY**, so que dessa vez colocando isso a nivel do modelo. O livro sai do pressuposto que o leitor ja conheca esse padrao, entao caso a pessoa nao conheca pode acabar ficando um pouco confusa a explicacao do autor.

# Composto
A ideia eh basicamente seguir a mesma logica do padrao **COMPOSITE**, so que dessa vez colocando isso a nivel do modelo. O design composite funciona basicamente da seguinte forma: 
Voce tem alguns objetos que dependem sempre de determinada informacao. Para voce garantir que todos terao pelo menos a mesma estrutura nos usamos uma **classe abstrata** que sera destinada a garantir a existencia de metodos padroes. Se por acaso quando herdar dessa classe precisar mudar as mudancas serao pontuais