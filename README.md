# Boas práticas C#
Olá! Esse guia tem como objetivo ajudá-lo a se tornar um desenvolvedor melhor, ajudando-o a escrever um código mais limpo, legível e eficaz. Apesar de ser voltado especificamente para C#, várias das dicas aqui apresentadas podem ser abstraídas para as mais diversas linguagens. Portanto fique atento e aproveite a leitura.


## Classes

* O nome da classe deve ser escrito em *Pascal Case*, ou seja, a primeira letra de cada palavra deve estar em maiúscula. **Ex.:** GatoPardo, CachorroGordo. *Inspirado por Martin Fowler*
* Cada arquivo *.cs* deve conter apenas uma classe. Colocar mais de uma classe em um arquivo prejudica sua legibilidade.
* As classes devem ter preferencialmente uma só responsabilidade. Ou seja, evitar que ela faça mais de uma coisa. **Ex.:** a classe SomaNumeros também fazer operação de subtração. *Inspirado por Martin Fowler*
* Evite criar construtores que recebem muito parâmetros, pois esse tipo de prática dificulta a utilização da classe. Em C# é fácil construir um objeto passando apenas os atributos desejado no momento de sua construção, evitando assim a necessidade de usar construtores com parâmetros. *Inspirado por Martin Fowler*
**Ex:.**
    ```
    new SomaNumeros
    {
        Valor1 = 10,
        Valor2 = 20
    }
    ```
* Dê nomes intuitivos para as classes criadas. Evite nomes que não representam a responsabilidade da classe. Classes que possuem uma única responsabilidade geralmente são mais fáceis de serem nomeadas. *Inspirado por Martin Fowler*
* Toda a classe deve ter um comentário em sua declaração, com um breve resumo sobre sua responsabilidade.
* Em C# não há necessidade de criar métodos *getter* e *setters* explícitamente, pois a linguagem já oferece uma *suggar sintaxe* para isso, prefira usar o padrão da linguagem. 
**Ex:.**

    ```
    public int Valor1 { get; private set; }
    ```
 * Sempre que possível utilize herança quando fizer sentido para o negócio, ou seja, quando houver uma clara relação entre as classes envolvidas, permitindo assim a reutilização inteligente de código.

## Atributos
* Atributos públicos devem ser escritos usando o padrão *Pascal Case*.
* Atributos protegidos devem ser escritos usando o padrão *Camel Case*.
* Atributos privados devem ser escritos usando o padrão *Camel Case*.
* Dê nomes intuitivos aos seus atributos que expressam o que eles representam. Evite nomes genéricos como *x*, a não ser que para o domínio do problema isso faça sentido. *Inspirado por Martin Fowler*
* Em regra um atributo de uma classe deve ser privado, devendo ser exposto para as classes filhas ou publicamente **apenas** se houver uma necessidade explícita. *Inspirado por Martin Fowler*

## Métodos
* Dê nome intuitivos a seus métodos que expressam sua responsabilidade. *Inspirado por Martin Fowler*
* Métodos devem ser simples e sucintos. Ou seja, idealmente devem ter apenas uma responsabilidade. Isso ajuda a mantê-los, a reusá-los e a testá-los. *Inspirado por Martin Fowler*
* Quanto menos parâmetros um método receber, melhor. Isso além de facilitar seu entendimento, também facilita o seu uso, pois ele vai ter menos dependência assim. *Inspirado por Martin Fowler*
* Evite colocar muitos "caminhos" em seu método. Ou seja, muitos *ifs*, *switch case*, *try catch*. Isso prejudica a manutenção do método, além de aumentar sua complexidade ciclomática. *Inspirado por Martin Fowler*
