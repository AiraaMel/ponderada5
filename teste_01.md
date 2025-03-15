# Instruções
- Faça uma cópia deste arquivo .md para um repositório próprio
- Resolva as 8 questões objetivas assinalando a alternativa correta e **justificando sua resposta.**
- Resolva as 2 questões dissertativas escrevendo no próprio arquivo .md
- Lembre-se de utilizar as estruturas de código como ``esta aqui com ` `` ou
```javascript
//esta aqui com ```
let a = "olá"
let b = 10
print(a)
```
- Resolva as questões com uso do Visual Studio Code ou ambiente similar.
- Teste seus códigos antes de trazer a resposta para cá.
- Cuidado com o uso de ChatGPT (e similares), pois entregar algo só para ganhar nota não fará você aprender. Não seja dependente da máquina!
- Ao final, publique seu arquivo lista_01.md com as respostas em seu repositório, e envie o link pela Adalove. 

# Questões objetivas
**1) Considerando a execução do código abaixo, indique a alternativa correta e justifique sua resposta.**
```javascript
console.log(x);
var x = 5;
console.log(y);
let y = 10;
```
``a) A saída será undefined seguido de erro``

b) A saída será 5 seguido de 10

c) A saída será undefined seguido de undefined

d) A saída será erro em ambas as linhas que utilizam console.log

``` javascript
    // x é definido com var, que é executado primeiro no codigo, entretato, ela terá como retorno o undefined, pois a variável é criada na memoria, mas um valor não foi denido. No caso de y, é utilizado let, entretanto, let não permite que a variavel seja executada antes da sua declaração, pois apenas é exevutado quando chega na linha dele, foi tentado usar a variavel antes de cria-lá.
```


**2) O seguinte código JavaScript tem um erro que impede sua execução correta. Analise e indique a opção que melhor corrige o problema. Justifique sua resposta.**

```javascript
function soma(a, b) {
    if (a || b === 0) {
        return "Erro: número inválido";
    }
    return a + b;
}
console.log(soma(2, 0));
```

a) Substituir if (a || b === 0) por if (a === 0 || b === 0)

``b) Substituir if (a || b === 0) por if (a === 0 && b === 0)``

c) Substituir if (a || b === 0) por if (a && b === 0)

d) Remover completamente a verificação if (a || b === 0)

``` javascript
    // O certo seria (a === 0 && b === 0) para a operação conseguir estar correta, pois quero algo que seja matematicamente inválido, assim se a e b fossem 0 a soma seria inválida
    // (a || b === 0) verifica se a é a e se b é igual a zero
    // ambos precisam ser igual a 0 para dar erro: número inválido
    // dessa forma, quando a e b são diferntes de 0 é possivel realizar a soma entre os elementos, no caso, quando ocorre a substituição no if obtém resultado 2.
```

______
**3) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
function calcularPreco(tipo) {
    let preco;

    switch(tipo) {
        case "eletrônico":
            preco = 1000;
        case "vestuário":
            preco = 200;
            break;
        case "alimento":
            preco = 50;
            break;
        default:
            preco = 0;
    }

    return preco;
}

console.log(calcularPreco("eletrônico"));
```

a) O código imprime 1000.

``b) O código imprime 200.``

c) O código imprime 50.

d) O código gera um erro.

``` javascript
    // O break é utilizado para sair resposta no switch, no console.log é pedido o preço do eletronico, no entanto, eletronico não possui break, assim, é procurado o break no proximo case, tendo como resultado a case vestuario, com valor de 200, que será imprimido.
    // break quebra o código, para algo, impedee que código continue a rodar dentro do switch
    // switch, qual o caso que irá funcionar (if/else em grande escala)
```
______
**4) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
let numeros = [1, 2, 3, 4, 5];

let resultado = numeros.map(x => x * 2).filter(x => x > 5).reduce((a, b) => a + b, 0);

console.log(resultado);
```
a) 0

b) 6

c) 18

``d) 24``

``` javascript
    // São realizadas operações e restrições no codigo, sendo definido que cada número é multiplicado por 2, em seguida são filtrados apenas resultados maiores que 5, no final soma os valores restantes. 
    // map percorre item por item realizando uma ação, no caso, ele pega um número dentro da array e multiplica por 2
    // filter percorre item por item, age como if, faz algo se for verdade, quando não é ele joga fora, não conta mais como item na lista
    // reduce inicia um novo array: o valor de a foi atribuido como (a+b) e o b recebeu valor inicial de 0, assim, o codigo fara a ação item por item, sendo assim: 6+0=6; 6+8=14; 14+10=24.

```
______
**5) Qual será o conteúdo do array lista após a execução do código? Indique a alternativa correta e justifique sua resposta.**

```javascript
let lista = ["banana", "maçã", "uva", "laranja"];
lista.splice(1, 2, "abacaxi", "manga");
console.log(lista);
```

a) ["banana", "maçã", "uva", "abacaxi", "manga", "laranja"]

b) ["banana", "abacaxi", "manga"]

``c) ["banana", "abacaxi", "manga", "laranja"]``

d) ["banana", "maçã", "uva", "abacaxi", "manga"]

``` javascript
    // A função splice é utilizada para alterar o conteudo de uma lista e adicionar novos elemntos, com isso, maça e uva estão na posição 1 e 2, sendo assim, eles serão substituidos por abacaxi e manga, ressultando em ["banana", "abacaxi", "manga", "laranja"].
```
______
**6) Abaixo há duas afirmações sobre herança em JavaScript. Indique a alternativa correta e justifique sua resposta**

I. A herança é utilizada para compartilhar métodos e propriedades entre classes em JavaScript, permitindo que uma classe herde os métodos de outra sem a necessidade de repetir código.  
II. Em JavaScript, a herança é implementada através da palavra-chave `extends`.


``a) As duas afirmações são verdadeiras, e a segunda justifica a primeira.``

b) As duas afirmações são verdadeiras, mas a segunda não justifica a primeira.

c) A primeira afirmação é verdadeira, e a segunda é falsa.

d) A primeira afirmação é falsa, e a segunda é verdadeira.

``` javascript
    // No POO, são utilizadas classes, que permitem a herança de metodos e propiedades dentro do código, o que evita repetição, para fazer isso, extends importa caracteristicas da classe 'mãe', para a classe filha, como quando uma classe cachorros, que possui caracteristicas especificas herda propiedades da classe mamiferos.
```

**7) Dado o seguinte código. Indique a alternativa correta e justifique sua resposta.**

```javascript
class Pessoa {
  constructor(nome, idade) {
    this.nome = nome;
    this.idade = idade;
  }

  apresentar() {
    console.log(`Olá, meu nome é ${this.nome} e tenho ${this.idade} anos.`);
  }
}

class Funcionario extends Pessoa {
  constructor(nome, idade, salario) {
    super(nome, idade);
    this.salario = salario;
  }

  apresentar() {
    super.apresentar();
    console.log(`Meu salário é R$ ${this.salario}.`);
  }
}
```


I) A classe Funcionario herda de Pessoa e pode acessar os atributos nome e idade diretamente.  
II) O método `apresentar()` da classe Funcionario sobrepõe o método `apresentar()` da classe Pessoa, mas chama o método da classe pai usando `super`.  
III) O código não funciona corretamente, pois Funcionario não pode herdar de Pessoa como uma classe, já que o JavaScript não suporta herança de classes.

Quais das seguintes afirmações são verdadeiras sobre o código acima?

``a) I e II são verdadeiras.``

b) I, II e III são verdadeiras.

c) Apenas II é verdadeira.

d) Apenas I é verdadeira.

``` javascript
    // Funcionario extend pessoa, com isso, o que pessoa possui é herdado por funcionario, no caso, nome e idade
    // classe filho consegue modificar o que classe mãe criou, no caso, funcionarios modifica o que havia em pessoa
    // super usa o da mãe e pode modificar
    // A afirmativa II é verdadeira pois a classe Funcionario consegue modificar o que a classe pessoa criou, assim, funcionario modifica o que havia em pessoa
```

______

**8) Analise as afirmações a seguir. Indique a alternativa correta e justifique sua resposta.**

**Asserção:** O conceito de polimorfismo em Programação Orientada a Objetos permite que objetos de diferentes tipos respondam à mesma mensagem de maneiras diferentes.  
**Razão:** Em JavaScript, o polimorfismo pode ser implementado utilizando o método de sobrecarga de métodos em uma classe.

a) A asserção é falsa e a razão é verdadeira.

``b) A asserção é verdadeira e a razão é falsa.``

c) A asserção é verdadeira e a razão é verdadeira, mas a razão não explica a asserção.

d) A asserção é verdadeira e a razão é verdadeira, e a razão explica a asserção.

``` javascript
    // A asserção está correta pois quando uma classe filha extends uma classe mãe é possível herdar, ou seja, o mesmo método pode ser utilizado de maneiras difentes. Entretanto, a razão está errada, pois javascript não suporta sobrecarga de métodos nativamente, se for definido um método com o mesmo nome ele sobreescreve o anterior.
```

______

# Questões dissertativas
9) O seguinte código deve retornar a soma do dobro dos números de um array, mas contém erros. Identifique os problema e corrija o código para que funcione corretamente. Adicione comentários ao código explicado sua solução para cada problema.

```javascript
function somaArray(numeros) {
    // foi adicionado var para iniciar a variáevel soma
    var soma = 0
    
    // i não havia sido declarado, com a adição var ele passa a ser declarado
    for (var i = 0; i < numeros.lenght; i++) {
        // com a substituição de = por += os valores são guardados
        soma += 2*numeros[i];
    }
    // retorna valor final da soma
    return soma;
}
// soma: 2+4+6+8=20
console.log(somaArray([1, 2, 3, 4]));
```
``` javascript
    // Soma não consegue ser executada pois ainda não possuia uma variavel somo
    // Como numero está relacionado ao tamanho do array, numeros.size deve ser substituido por numeros.lenght 
    // A variavel i precisa ser declarada para o código conseguir ser executado
    // A forma anterior do código sobreescrvia a resposta obtida anteriomente, assim, os valores que vinham antes eram perdidos com a mudança no código soma acumula o dobro de cada número.
```
______
10) Crie um exemplo prático no qual você tenha duas classes:

- Uma classe `Produto` com atributos `nome` e `preco`, e um método `calcularDesconto()` que aplica um desconto fixo de 10% no preço do produto.

```javascript
// Classe do produto
class Produto {
    // Definindo atributos de nome e preço
    constructor(nome, preco) {
    this.nome = nome;
    this.preco = preco;
    }

    // Método para calcular valor após desconto de 10%
    calcularDesconto() {
        // A porcentagem do desconto é fixa de 10%
        let desconto = 10;
        // Cauculo do desconto
        let valorDesconto = (this.preco * desconto) / 100;
        // Valor final
        return this.preco - valorDesconto;
    }
}
    
    // Cria produto para testar código
    let produtoTeste = new Produto("Fone", 100)

    // Imprime preço após desconto
    console.log("O produto", produtoTeste.nome, "após desconto tem valor de", produtoTeste.calcularDesconto());
```

- Uma classe `Livro` que herda de `Produto` e modifica o método `calcularDesconto()`, aplicando um desconto de 20% no preço dos livros.

Explique como funciona a herança nesse contexto e como você implementaria a modificação do método na classe `Livro`.
``` javascript
    // Classe do produto
    class Produto {
    // Definindo atributos de nome e preço
    constructor(nome, preco) {
        this.nome = nome;
        this.preco = preco;
    }

    // Método para calcular valor após desconto de 10%
    calcularDesconto() {
        // A porcentagem do desconto é fixa de 10%
        let desconto = 10;
        // Cauculo do desconto
        let valorDesconto = (this.preco * desconto) / 100;
        // Valor final
        return this.preco - valorDesconto;
    }
}

// Classe livro, que herda de produto, por meio do extends
class Livro extends Produto {
    constructor(nome, preco, editora) {
        // chama construtor da classe pai
        super(nome, preco);
        // Define atributo editora
        this.editora = editora;
    }

    // Método sobrescrito para calcular o desconto do livro
    calcularDesconto() {
        // Primeiro, aplica o desconto de 10% da classe Produto
        let precoComDesconto = super.calcularDesconto();
        // Depois, aplica um desconto adicional de 20% sobre o preço já com desconto
        precoComDesconto = precoComDesconto - (precoComDesconto * 20) / 100;
        // Imprime novo valor
        console.log(`O livro "${this.nome}" da editora ${this.editora} custa: R$${precoComDesconto.toFixed(2)}`);
        // Retorna o preço final com os descontos aplicados
        return precoComDesconto;
    }
}

// Objeto da classe livro e teste
let livro = new Livro("Comece pelo porquê", 75, "Simon Sinek");
// Chama o método calcularDesconto para obter o preço final do livro
livro.calcularDesconto();

// No código acima possui duas classes, uma pai: Produto e uma filha: Livro, Produto caucula um desconto de 10% e possui os atributos nome e preco, que são herdados em Livro, o método calcular desconto é sobrescrito para adicionar desconto de mais 20%. Quando utilizado super, é garantido que seja aplicado o desconto de antes do novo cálculo. Assim, produto tem desconto de apenas 10%, enquanto livro recebe 20% sobre os 10%.
```