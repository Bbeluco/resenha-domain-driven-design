A vantagem de termos um modelo bem definido (e um codigo que replique este modelo) eh que assim conseguiremos a partir do codigo expressar exatamente quais sao as dores dos usuarios.

A tendencia natural das coisas eh que voce e a equipe de negocios utilizem o mesmo linguajar. Se por algum acaso voce estiver sendo sempre corrigido na forma de se expressar isso pode ser um bom indicatiivo que voce nao entendeu determinado conceito completamente. Deixar lacunas no entendimento no conceito geram lacunas no desenvolvimento do modelo que por sua vez levam a lacunas na solucao apresentada.

Alguns conceitos implicitos do modelo podem causar maiores complicacoes na hora de nos comunicarmos, o ideial eh que, caso a gente identifique algo critico para o dominio que esta sendo representado de forma implicita no modelo, refacamos o modelo, representado isolando a parte implicita.

O processo para entendermos bem como determinado dominio (nesse caso no sentido de temos uma necessidade X e vamos atras da solucao) funciona leva VARIAS e VARIAS tentativas, porem, a cada tentativa que temos, mais uma chance tambem eh criada para criar pontos de flexibilidade na modelagem.

Como modelagem nao se restringe somente a diagramas, vamos agora dar um exemplo siim de modelagem de codigo que segundo o autor contem maiores vantagens. Imagine o seguinte cenario: 

_Vamos fazer uma funcao que determinada a quantidade de liquido que vai em um balde_

Exemplo1.Java
```Java
public class Balde {
    private float volumeAtual;
    private float capacidadeTotal;

    public float quantidadeVolume(float volumeAAdicionar) {
        if(volumeAAdicionar + volumeAtual > capacidadeTotal) {
            volumeAtual = capacidadeTotal;
        } else {
            volumeAtual += volumeAAdicionar;
        }

        return volumeAtual;
    }
}
```

Exemplo2.Java
```Java
public class Balde {
    private float volumeAtual;
    private float capacidadeTotal;

    public float adicionarVolume(float volumeAAdicionar) {
        float volumeDesejado = volumeAtual + volumeAAdicionar;
        volumeAtual = verificarVolume(volumeDesejado);
    }

    public float verificarVolume(float volumeAAdicionar) {
        if(volumeAAdicionar > capacidadeTotal) return capacidadeTotal;
        return volumeAAdicionar;
    }
}
```

Segundo o autor, caso a gente compare esses 2 exemplos o segundo sera mais alinhado ao desenvolvimento baseado em modelo. Mas pq?

Isso acontece pois no Exemplo2.java temos de facil entendimento como saber de onde determinadas regras de negocio vem, tornando assim mais explicito o modo de funcionamento da nossa aplicacao. Obvio que no Exemplo1 ele o codigo tambem eh funcional mas pode acabar gerando a duvida "_Pq determinada regra esta assim e nao de outra forma?_"

**Se as regras de negocio estao comecando a sobrecarregar o objeto ou fugindo das restricoes do dominio, eh recomendado que isolemos essas questoes em classes separadas**

# Especificacao
Nunca devemos remover as regras de negocio da camada de dominio pois o codigo deixaria de expressar o modelo.

A ideia de criarmos especificacoes eh basicamente a seguinte:

Vamos testar nosso objeto uma condicao true ou false (atraves de predicados), se a operacao ocorrer conforme nos esperavamos basicamente sera criado um novo objeto a partir dela.

Eh como se fosse um """.filter""" do JavaScript, se a operacao der boa vai sair um objeto dela, se nao, vai sair undefined.

Indo mais a fundo uma especificacao pode ter 3 funcionalidades

- Validar um objeto -> Equivalente ao .some do JS
- Selecionar um objeto -> Equivalente ao .filter do JS
- Especificar a criacao de um novo objeto

Esse ultimo ele eh mais o seguinte conceito:

Quero um carro que tenha cor preta, atinja 300km/h e que faca 10Km/L

Isso que eu passei agora foram as ESPECIFICACOES de um carro que quero adquirir, como a fabricante vai fazer pra conseguir ter como resultado um carro desse nao me interessa, interessa apenas que pedi e espero que algo assim apareca para mim.