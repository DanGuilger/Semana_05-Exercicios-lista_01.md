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
a) A saída será undefined seguido de erro (Resposta certa)

Justificativa - O console.log(x) retorna undefined porque a variável é declarada depois, mas como foi definida com var, o JavaScript a reconhece antes da atribuição de valor. Já a variável y, declarada com let, só pode ser acessada após sua inicialização, causando um erro ao tentar usá-la antes disso.

b) A saída será 5 seguido de 10

c) A saída será undefined seguido de undefined

d) A saída será erro em ambas as linhas que utilizam console.log


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

a) Substituir if (a || b === 0) por if (a === 0 || b === 0) (Resposta certa)

Justificativa: A alternativa A foi escolhida porque a condição do if está incorreta. O operador || faz com que a variável b seja avaliada primeiro, e como b === 0 retorna true, o if é acionado, impedindo a soma de ser executada. A correção adequada é garantir que ambas as variáveis sejam verificadas corretamente, como na alternativa A.

b) Substituir if (a || b === 0) por if (a === 0 && b === 0)

c) Substituir if (a || b === 0) por if (a && b === 0)

d) Remover completamente a verificação if (a || b === 0)

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

b) O código imprime 200. (Resposta certa)

Justificativa: O valor impresso é 200 porque, embora o argumento seja "eletrônico", o código não possui um break após esse case. Isso faz com que a execução continue até o próximo case com break, que é "vestuário", resultando na atribuição do valor 200 antes de encerrar a execução.

c) O código imprime 50.

d) O código gera um erro.

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

d) 24 (Resposta certa)

Justificativa: Primeiro, o método map transforma cada número do array multiplicando por 2, criando [2, 4, 6, 8, 10]. Em seguida, o filter seleciona apenas os valores maiores que 5, ficando com [6, 8, 10]. Por último, o reduce soma esses números, resultando em 24.
______
**5) Qual será o conteúdo do array lista após a execução do código? Indique a alternativa correta e justifique sua resposta.**

```javascript
let lista = ["banana", "maçã", "uva", "laranja"];
lista.splice(1, 2, "abacaxi", "manga");
console.log(lista);
```

a) ["banana", "maçã", "uva", "abacaxi", "manga", "laranja"]

b) ["banana", "abacaxi", "manga"]

c) ["banana", "abacaxi", "manga", "laranja"] (Resposta certa)

Justificativa: O método splice(1, 2) indica que a remoção começa no índice 1 (segunda posição) e elimina dois elementos, que são "maçã" e "uva". Em seguida, os itens "abacaxi" e "manga" são inseridos exatamente no local onde os anteriores foram removidos, mantendo a ordem do restante do array.

d) ["banana", "maçã", "uva", "abacaxi", "manga"]
______
**6) Abaixo há duas afirmações sobre herança em JavaScript. Indique a alternativa correta e justifique sua resposta**

I. A herança é utilizada para compartilhar métodos e propriedades entre classes em JavaScript, permitindo que uma classe herde os métodos de outra sem a necessidade de repetir código.  
II. Em JavaScript, a herança é implementada através da palavra-chave `extends`.


a) As duas afirmações são verdadeiras, e a segunda justifica a primeira. (Resposta certa)

Justificativa: Em JavaScript, a herança possibilita que uma classe reutilize métodos e propriedades de outra, reduzindo a duplicação de código e tornando a manutenção mais eficiente. Isso é implementado com a palavra-chave extends, permitindo que uma classe filha herde funcionalidades da classe pai.

b) As duas afirmações são verdadeiras, mas a segunda não justifica a primeira.

c) A primeira afirmação é verdadeira, e a segunda é falsa.

d) A primeira afirmação é falsa, e a segunda é verdadeira.
______
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

a) I e II são verdadeiras. (Resposta certa)

Justificativa: A afirmação I é verdadeira, pois ao estender a classe Pessoa, a classe Funcionario herda automaticamente seus atributos e métodos, sendo necessário chamar super para inicializar os valores da classe pai. A afirmação II também é verdadeira, pois super.apresentar() executa o método da classe pai antes da nova implementação na classe filha, garantindo a ordem correta na saída. Já a afirmação III é falsa, pois JavaScript suporta herança de classes por meio da palavra-chave extends.

b) I, II e III são verdadeiras.

c) Apenas II é verdadeira.

d) Apenas I é verdadeira.

______

**8) Analise as afirmações a seguir. Indique a alternativa correta e justifique sua resposta.**

**Asserção:** O conceito de polimorfismo em Programação Orientada a Objetos permite que objetos de diferentes tipos respondam à mesma mensagem de maneiras diferentes.  
**Razão:** Em JavaScript, o polimorfismo pode ser implementado utilizando o método de sobrecarga de métodos em uma classe.

a) A asserção é falsa e a razão é verdadeira.

b) A asserção é verdadeira e a razão é falsa.

c) A asserção é verdadeira e a razão é verdadeira, mas a razão não explica a asserção. (Resposta certa)

Justificativa: Na Programação Orientada a Objetos (POO), o polimorfismo permite que métodos com o mesmo nome tenham comportamentos distintos em diferentes classes, adaptando-se ao objeto que os chama. No JavaScript, não há suporte nativo para sobrecarga de métodos, mas ela pode ser simulada ajustando a lógica dentro de um único método, com verificações de parâmetros. Portanto, embora a afirmação sobre a sobrecarga esteja correta, ela não é a abordagem principal para polimorfismo na linguagem, que ocorre principalmente por meio da herança e da sobrescrita de métodos.

d) A asserção é verdadeira e a razão é verdadeira, e a razão explica a asserção.

______

# Questões dissertativas
9) O seguinte código deve retornar a soma do dobro dos números de um array, mas contém erros. Identifique os problema e corrija o código para que funcione corretamente. Adicione comentários ao código explicado sua solução para cada problema.

```javascript
function somaArray(numeros) {

    for (i = 0; i < numeros.size; i++) {
        soma = 2*numeros[i];
    }
    return soma;
}
console.log(somaArray([1, 2, 3, 4]));
```

Justificativa:

```javascript

function somaArray(numeros) {
    let soma = 0; //Variável inicializada com 0 para armazenar o total acumulado.

    for (let i = 0; i < numeros.length; i++) { //Iteração sobre todos os elementos do array utilizando .length.
        soma += 2 * numeros[i]; //Multiplica cada número por 2 e adiciona ao total acumulado.
    }
    }

    return soma; //Retorna o resultado final da soma dos valores dobrados.
}

console.log(somaArray([1, 2, 3, 4])); //Saída esperada: 20 (2+4+6+8)

```
______
10) Crie um exemplo prático no qual você tenha duas classes:

- Uma classe `Produto` com atributos `nome` e `preco`, e um método `calcularDesconto()` que aplica um desconto fixo de 10% no preço do produto.
- Uma classe `Livro` que herda de `Produto` e modifica o método `calcularDesconto()`, aplicando um desconto de 20% no preço dos livros.

Explique como funciona a herança nesse contexto e como você implementaria a modificação do método na classe `Livro`.

Justificativa:

```javascript

//Classe Produto com nome, preço e método para calcular desconto
class Produto {
    constructor(nome, preco) {
        this.nome = nome;
        this.preco = preco;
    }

    //Método que aplica um desconto de 10% ao preço do produto
    calcularDesconto() {
        return this.preco * 0.90;
    }
}

//Classe Livro que herda de Produto e modifica o método calcularDesconto
class Livro extends Produto {
    constructor(nome, preco, autor) {
        super(nome, preco); //Chama o construtor da classe Produto
        this.autor = autor; //Novo atributo exclusivo para livros
    }

    //Método sobrescrito para aplicar um desconto de 20%
    calcularDesconto() {
        return this.preco * 0.80;
    }
}

//Exemplo de uso
const produtoGeral = new Produto("Smartphone", 1000);
const livro = new Livro("JavaScript Avançado", 150, "John Doe");

console.log(`Preço do ${produtoGeral.nome} com desconto: R$ ${produtoGeral.calcularDesconto()}`); // 900
console.log(`Preço do livro '${livro.nome}' com desconto: R$ ${livro.calcularDesconto()}`); // 120

```

A classe Produto define nome, preco e um método calcularDesconto() com 10% de desconto. A classe Livro herda de Produto com extends, mantendo os atributos e métodos, mas adicionando autor e sobrescrevendo calcularDesconto() para aplicar 20% de desconto. O uso de super(nome, preco) garante a correta inicialização dos atributos herdados. Esse processo exemplifica polimorfismo, permitindo que métodos tenham comportamentos diferentes conforme a classe, otimizando a reutilização do código.