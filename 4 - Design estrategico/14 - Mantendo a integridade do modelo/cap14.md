Eh inerante quando criamos um modelo **ser consistente** (todos os pontos da aplicacao pensam da mesma forma, o nome tecnico eh _unificacao_)

O problema da afirmacao anterior eh que quanto maior a empresa, maior o modelo e consequentemente mais dificil fica alcancar esse nivel de consistencia esperado. A tendencia eh que as coisas fiquem baguncadas, tudo caminha para a entropia. Faz parte da capacidade tecnica da equipe que esta modelando o sistema garantir por via do esforco que o modelo tera a consistencia esperada.

A fala do autor nesse comeco de capitulo da a entender que ele esta falando de uma empresa que organiza sua arquitetura de software em um grande monolito, sendo assim, eh criada 2 ideias:

**Contexto delimitado**: O que determinada equipe pode propor de modelo para sua determinada realidade
**Mapa de contexto**: um diagrama contendo todos os conceitos criados ate entao

# Contexto delimitado
Eh bem verdade que quando temos um grande projeto teremos como senquencia tambem VARIOS MODELOS. Isso acontece pq cada equipe tem a sua determinada necessidade, o que reflete em determinado modelo e tudo mais. A recomendacao do autor nesse caso eh a seguinte: **nao reaproveite modelo de outra equipe para sua realidade**. Ao reaproveitar modelos para sua realidade voce basicamente esta criando uma anomalia baseada no codigo que faz sentido no contexto de outros. Voce sim, pode se basear em "padroes de projeto", mas sempre deve criar o seu proprio para a SUA realidade

Um modelo so fara sentido em um **determinado contexto**, dai que surge a ideia de _contexto delimitado_

_Beleza, mas qual eh o ganho de delimitar o contexto do modelo?_
Para equipes que estao trabalhando no modelo, a garantia eh que elas devem se preocupar so com elas mesmas, nao precisando se importar se aquele determinado modelo vai quebrar a modelagem de outra equipe.

E para equipes que nao estao trabalhando nesse modelo eh a garantia que eles nao serao impactados por fatores que ocorrem dentro dessa "caixa" (que eh o modelo que outra equipe esta tocando)

# Integracao continua
A ideia eh exatamente o que a gente conhece hoje como CI/CD (nesse caso so a parte do CI). O ganho que temos nisso eh que se subirmos algo e o contexto tiver saindo um pouco de ponto, todo mundo vai verificar isso e rapidamente vao corrigir. Tendo a premissa que comunicacao sempre eh algo super complexo de fazer, garantir que codigo suba toda hora teria o mesmo efeito de uma conversa entre 2 pessoas ao vivo. Se uma pessoa errar uma palavra/ideia a outra identifica na hora, diferente do efeito de uma carta por exemplo

## Nucleo compartilhado
A ideia eh basicamente a seguinte:

temos 2 equipes, as 2 vao acabar usando a parte X do modelo. Ao inves de criarmos codigos duplicados, como ambas estao alterando mesmo lugar nos criamos um pacto que esse nucleo so eh alterado se as 2 partes estiverem de acordo (e obviamente o nucleo precisa estar coberto por testes). Dessa forma, garantiremos que o nosso modelo ainda tera contextos bem definidos so que agora com multipla participacao

## Anticorruption layer
A ideia eh basicamente a seguinte:

Voce tem um sistema A que depende do sistema B. 
O sistema B eh legado e ele sera migrado. 
Na migracao eh criado B2.
B2 nao se comporta exatamente como B e por isso apresenta side effects no sistema A
Uma camada de _anticorruption_ eh criada so pro sistema A ir se comunicando com o sistema B2 como se estivesse falando com o legado

(Isso acontece pq em migracoes mesmo que somente de tipos primitivos podemos acabar tendo comportamentos diferentes dada a plataforma. Entao eh mais seguro so criar uma camada de comunicacao pra nao impactar os "clientes" daquele codigo)