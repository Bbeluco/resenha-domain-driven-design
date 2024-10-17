Antigamente para se resolver determinado problema (ou melhor dizendo, dominio), desenvolvedores criavam o codigo mais enxuto possivel, geralmente nao se importando muito em separacao de responsabilidades. Era basicamente uma UI que dava query direto no banco de dados. Isso por mais que fosse mais rapido, a medida que o sistema crescia fazer manutencao nesses sistemas se tornavam um verdadeiro desafio.

Foi pensando nesse ponto que foi criada a **arquitetura em camadas**, o livro aqui tem uma explicacao bem similar a do livro _Fundamentos da Arquitetura de Software_, basicamente a arquitetura em camadas nos permite dividir o sistema de modo que parte dele eh responsavel por executar apenas um tipo de funcao; essa separacao faz com que as manutencoes sejam mais simples de serem executadas, e caso o sistema necessite de atualizacoes elas nao vai gerar grandes impactos alem do esperado.

_OBS: caso queira no futuro revisar recomendo rever o livro dos "fundamentos da arquitetura de software" 
la (na minha opiniao) eh mais rico em detalhes sobre esse tipo de camada_

No livro o autor eh sempre bem enfatico ao dizer na visao dele que nao importa como todas as camadas serao construidas **desde que a camada de dominio seja isolada do sistema**. A camada de dominio que ele tanto fala eh o que conhecemos hoje como camada de **servicos**.

Uma camada de servicos geralmente tem ligacao direta com a camada de infraestrutura (ou como conhecemos hoje, camada de **repositories**). A ideia eh a seguinte: Nao importa como a camada de repository vai implementar meu banco de dados, se ele vai ser o A, B ou C. O importante eh que vou rodar o comando _dbRepository.save()_ e as minhas informacoes serao salvas no banco. Pra camada de servicos isso acontece de forma completamente oculta.

## Anti-pattern "UI inteligente"
Aqui o autor chega na seguinte conclusao: DDD deve ser usado em projetos ambiciosos e complexos, nao faz sentido colocarmos DDD em sistemas simples. Se o sistema for de fato simples, coloca a logica de negocios direto na UI do usuario mesmo (apenas tome cuidado em modularizar bem as funcionalidades). Dessa forma voce entregara o sistema de forma rapida e pratica.

Em linhas gerais essa abordagem tem como principal vantagem a rapida adaptacao dos desenvolvedores envolvidos (tendo em vista que ate mesmo desenvolvedores menos experientes conseguirao entender com facilidade esse tipo de organizacao). O principal defeito eh que nao da pra voltar atras na escolha, escolher o caminho de UIs inteligentes faz com que caso voce tenha que mudar o sistema para _Design Dirigido a Modelos_ voce tenha que reescrever absolutamente tudo do zero.