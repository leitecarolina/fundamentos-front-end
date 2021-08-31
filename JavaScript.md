# JavaScript

### O QUE É JAVASCRIP

JavaScript é uma linguagem de programação que permite a você implementar itens complexos em páginas web — toda vez que uma página da web faz mais do que simplesmente mostrar a você informação estática — mostrando conteúdo que se atualiza em um intervalo de tempo, mapas interativos ou gráficos 2D/3D animados, etc.

### JS para web VS node.js

A grande diferença entre o JS e node, é que node é a forma de programar em javascript fora do navegador.

Links:

- [https://github.com/GitbookIO/javascript/blob/master/SUMMARY.md](https://github.com/GitbookIO/javascript/blob/master/SUMMARY.md)

---

### COMENTÁRIOS

```jsx
// This is a comment, it will be ignored by the interpreter
/*
This is a multi-line comment,
it will be ignored by the interpreter
*/
```

---

### OPERAÇÕES

You can apply mathematic operations to numbers using some basic operators like:

- **Addition**: `c = a + b`
- **Subtraction**: `c = a - b`
- **Multiplication**: `c = a * b`
- **Division**: `c = a / b`
- **Modulus (division remainder)**: `x = y % 2`
- **Increment**: Given a = 5
    - `c = a++`, Results: c = 5 and a = 6
    - `c = ++a`, Results: c = 6 and a = 6
- **Decrement**: Given a = 5
    - `c = a--`, Results: c = 5 and a = 4
    - `c = --a`, Results: c = 4 and a = 4

Precedência:  `()` → `**` → `*`, `/`, `%` → `+`, `-`

---

### UTILIZAÇÃO "="

- n = 5:  a variável n *recebe* 5.
- 5 == '5'  e  5 == 5:  são  *iguais* em valor. **
- 5 === '5':  não são *idênticos*, possuem mesmo valor mas tipos diferentes.

---

### CONDICIONAIS

- If: The condition has to be true for the code inside the curly braces to be executed: `if(condition){ do this … }`
- Exemplo

    ```jsx
    var country = "France";
    var weather;
    var food;
    var currency;

    if (country === "England") {
      weather = "horrible";
      food = "filling";
      currency = "pound sterling";
    }

    if (country === "France") {
      weather = "nice";
      food = "stunning, but hardly ever vegetarian";
      currency = "funny, small and colourful";
    }

    if (country === "Germany") {
      weather = "average";
      food = "wurst thing ever";
      currency = "funny, small and colourful";
    }

    var message =
      "this is " +
      country +
      ", the weather is " +
      weather +
      ", the food is " +
      food +
      " and the " +
      "currency is " +
      currency;
    ```

- Else: There is also an else clause that will be applied when the first condition isn’t true. This is very powerful if you want to react to any value, but single out one in particular for special treatment
- Exemplo

    ```jsx
    var umbrellaMandatory;

    if (country === "England") {
      umbrellaMandatory = true;
    } else {
      umbrellaMandatory = false;
    }

    //

    if (country === "England") {
      ...
    } else if (country === "France") {
      ...
    } else if (country === "Germany") {
      ...
    }
    ```

- Comparadores:  `x > a`, `x < a`, `x <= a`, `x >=a`, `x != a`, `x`, `x==a`, `x===a`
- Exemplo

    ```jsx
    if (country === "France") {
        ...
    }

    /* Three equal signs tests 
    if the variable country has both the correct 
    value (France) and also the correct type (String) */
    ```

- Concatenar: OU - `||` , E - `&&`
- Exemplo

    ```jsx
    if (x > 10 && x < 20) {
        ...
    }
    ```

- Exemplos aplicações web
- Exemplo 1

    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>DETRAN</title>
    </head>
    <body>
        <h1>Sistemas de Multas</h1>
        Velocidade do carro: <input type="number" name="txtvel" id="txtvel"> km/h
        <input type="button" value="Verificar" onclick="calcular()">
        <div id="res"></div>

        <script>
            function calcular() {
                var txtv = document.querySelector('input#txtvel')
                var res = document.querySelector('div#res')
                var vel = Number(txtv.value)
                res.innerHTML = `<p>Sua velocidade atual é de <strong>${vel}km/h<strong></p>`
                if (vel>60 ) {
                    res.innerHTML += `Você está multado`
                }    
                res.innerHTML += `<p>Dirija sempre com cinto de segurança!</p>`
            }
        </script>
    </body>
    </html>
    ```

---

### LOOPS

- For:  iterar em cada linha. Sintaxe:

```jsx
for (condition; end condition; change) {
    // do it, do it now
}
```

- Exemplo

    ```jsx
    for (var i = 0; i < 10; i = i + 1) {
      // do this code ten-times
    }

    /* iniciando com i = 0 e indo até i menores que 10, 
    faça i + 1 */
    ```

- While: enquanto uma condição for verdadeira faça

```jsx
while (condition) {
  // do it as long as condition is true
}
```

- Exemplo

    ```jsx
    var i = 0,
      x = "";
    while (i < 5) {
      x = x + "The number is " + i;
      i++;
    }
    ```

- Do While: criar um um loop que executa uma instrução específica até que a condição de teste seja falsa

```python
do {
  // statement
} while (expression);
```

- Exemplo

    ```jsx
    var i = 0;
    do {
      document.write(i + " ");
      i++; // incrementing i by 1
    } while (i < 10);

    // print numeros menores que 10 
    ```

---

### OBJETOS

Os tipos primitivos em JS são true, false, number, strings, null e undefined. Todo o resto é considerado um objeto.

- Criando um objeto

    Existem duas maneiras:

    1. literal

    ```jsx
    var object = {};
    ```

    1. Orientado a objeto

    ```jsx
    var object = new Object();
    ```

- Propriedades

    A propriedade do objeto é um par `propertyName`: `propertyValue`, onde o nome da propriedade pode ser apenas uma string. Se não for uma string, é fundido em uma string. Você pode especificar propriedades ao criar um objeto ou posteriormente. Pode haver zero ou mais propriedades separadas por vírgulas.

    ```jsx
    var language = {
      name: "JavaScript",
      isSupportedByBrowsers: true,
      createdIn: 1995,
      author: {
        firstName: "Brendan",
        lastName: "Eich",
      },
      // Yes, objects can be nested!
      getAuthorFullName: function () {
        return this.author.firstName + " " + this.author.lastName;
      },
      // Yes, functions can be values too!
    };
    ```

    O código a seguir demonstra como obter o valor de uma propriedade:

    ```jsx
    var variable = language.name;
    // variable now contains "JavaScript" string.
    variable = language["name"];
    // The lines above do the same thing. The difference is that the second one lets you use litteraly any string as a property name, but it's less readable.
    variable = language.newProperty;
    // variable is now undefined, because we have not assigned this property yet.
    ```

    O exemplo a seguir mostra como adicionar uma nova propriedade ou alterar uma existente:

    ```jsx
    language.newProperty = "new value";
    // Now the object has a new property. If the property already exists, its value will be replaced.
    language["newProperty"] = "changed value";
    // Once again, you can access properties both ways. The first one (dot notation) is recomended.
    ```

- Mutáveis

    A diferença entre objetos e valores primitivos é que podemos mudar os objetos, enquanto os valores primitivos são imutáveis:

    ```jsx
    var myPrimitive = "first value";
    myPrimitive = "another value";
    // myPrimitive now points to another string.
    var myObject = { key: "first value" };
    myObject.key = "another value";
    // myObject points to the same object.
    ```

- Referência

    Objetos nunca são copiados. Eles são transmitidos por referência:

    ```jsx
    // Imagine I had a pizza
    var myPizza = { slices: 5 };
    // And I shared it with You
    var yourPizza = myPizza;
    // I eat another slice
    myPizza.slices = myPizza.slices - 1;
    var numberOfSlicesLeft = yourPizza.slices;
    // Now We have 4 slices because myPizza and yourPizza
    // reference to the same pizza object.

    var a = {},
      b = {},
      c = {};
    // a, b, and c each refer to a
    // different empty object
    a = b = c = {};
    // a, b, and c all refer to
    // the same empty object
    ```

- Prototype

    Cada objeto está vinculado a um objeto protótipo do qual herda propriedades.
    Todos os objetos criados a partir de literais de objeto ({}) são automaticamente vinculados a Object.prototype, que é um objeto que vem como padrão com JavaScript.
    Quando um interpretador de JavaScript (um módulo em seu navegador) tenta encontrar uma propriedade, que você deseja recuperar, como no código a seguir:

    ```jsx
    var adult = { age: 26 },
      retrievedProperty = adult.age;
    // The line above
    ```

    Primeiro, o interpretador examina todas as propriedades que o próprio objeto possui. Por exemplo, adulto possui apenas uma propriedade - idade. Mas, além desse, ele realmente tem mais algumas propriedades, que foram herdadas de Object.prototype.

    ```jsx
    var stringRepresentation = adult.toString();
    // the variable has value of '[object Object]'
    ```

    `toString` é uma propriedade de Object.prototype, que foi herdada. Ele tem o valor de uma função, que retorna uma representação em string do objeto. Se você quiser que ele retorne uma representação mais significativa, poderá substituí-lo. Basta adicionar uma nova propriedade ao objeto adulto.

    ```jsx
    adult.toString = function () {
      return "I'm " + this.age;
    };
    ```

    Se você chamar a função toString agora, o interpretador encontrará a nova propriedade no próprio objeto e parará.
    Assim, o interpretador recupera a primeira propriedade que encontrará no caminho do próprio objeto e posteriormente por meio de seu protótipo.
    Para definir seu próprio objeto como um protótipo em vez do Object.prototype padrão, você pode invocar Object.create da seguinte maneira:

    ```jsx
    var child = Object.create(adult);
    /* This way of creating objects lets us easily replace the default Object.prototype with the one we want. In this case, the child's prototype is the adult object. */
    child.age = 8;
    /* Previously, child didn't have its own age property, and the interpreter had to look further to the child's prototype to find it.
     Now, when we set the child's own age, the interpreter will not go further.
     Note: adult's age is still 26. */
    var stringRepresentation = child.toString();
    // The value is "I'm 8".
    /* Note: we have not overridden the child's toString property, thus the adult's method will be invoked. If adult did not have toString property, then Object.prototype's toString method would be invoked, and we would get "[object Object]" instead of "I'm 8" */
    ```

    O protótipo de `child` é `adult`, o qual o protótipo é `Object.prototype` . Essa sequencia de protótipos é chamada de prototype chain (cadeia de protótipos).

- Delete

    `delete` pode ser usado para remover uma propriedade de um objeto. Ele removerá uma propriedade do objeto, se houver. Não vai procurar mais na cadeia de protótipos. Remover uma propriedade de um objeto pode permitir que uma propriedade da cadeia de protótipos brilhe através de:

    ```jsx
    var adult = { age: 26 },
      child = Object.create(adult);
    child.age = 8;

    delete child.age;
    /* Remove age property from child, revealing the age of the prototype, because then it is not overriden. */
    var prototypeAge = child.age;
    // 26, because child does not have its own age property.
    ```

- Enumeração

    A instrução `for in` pode repetir todos os nomes de propriedade em um objeto. A enumeração incluirá funções e propriedades de protótipo.

    ```jsx
    var fruit = {
        apple: 2,
        orange: 5,
        pear: 1,
      },
      sentence = "I have ",
      quantity;
    for (kind in fruit) {
      quantity = fruit[kind];
      sentence += quantity + " " + kind + (quantity === 1 ? "" : "s") + ", ";
    }
    // The following line removes the trailing coma.
    sentence = sentence.substr(0, sentence.length - 2) + ".";
    // I have 2 apples, 5 oranges, 1 pear.
    ```

- Global footprint

    Se você estiver desenvolvendo um módulo, que pode estar em execução em uma página da web, que também executa outros módulos, deve tomar cuidado com a sobreposição do nome da variável.
    Suponha que estejamos desenvolvendo um módulo de contador:

    ```jsx
    var myCounter = {
      number: 0,
      plusPlus: function () {
        this.number = this.number + 1;
      },
      isGreaterThanTen: function () {
        return this.number > 10;
      },
    };
    ```

    O módulo agora leva apenas um nome de variável - `myCounter`. Se qualquer outro módulo na página fizer uso de nomes como `number` ou `isGreaterThanTen,` então é perfeitamente seguro, porque não substituiremos os valores uns dos outros;

---

### VARIÁVEIS

- Números: float e int
- String:  a line of text like "boat", "elephant" or "damn, you are tall!"
- Boolean: either true or false, but nothing else
- Arrays: são geralmente descritas como "lista de objetos"; elas são basicamente objetos que contem múltiplos valores armazenados em uma lista.
- Objects: a representation of a more complex object
- Null: a variable that contains null contains no valid Number, String, Boolean, Array, or Object
- Undefined: the undefined value is obtained when you use an object property that does not exist, or a variable that has been declared, but has no value assigned to it.

---

### STRINGS

```jsx
// Single quotes can be used
var str = 'Our lovely string';

// Double quotes as well
var otherStr = "Another nice string";

// Concatenation
var bigStr = "Hi " + "JS strings are nice " + "and " + "easy to add";

// Just use the property .length
var size = "Our lovely string".length;
```

---

### TEMPLATE STRINGS

Podemos usar o template strings para facilitar a concatenação. Sempre usar:

- Entre acentos agudos `......`
- Entre ${........}

```jsx
var name = 'Carolina'
var lastname = 'Leite'

document.write(`Meu nome é ${name} e meu sobrenpme é ${lastname})
```

---

### ARRAYS

Arrays são uma parte fundamental da programação. Um array é uma lista de dados. Podemos armazenar muitos dados em uma variável, o que torna nosso código mais legível e fácil de entender. Também torna muito mais fácil executar funções em dados relacionados. Os dados dentro do array sã chamados de elementos.

```jsx
var random = ['tree', 795, [0, 1, 2]];
```

---

### FUNÇÕES

- Função simples: Funções como funções matemáticas realizam transformações, elas pegam valores de entrada chamados argumentos e retornam um valor de saída. As funções são declaradas como:

```jsx
function double(x) {
  return 2 * x;
}

// também podem ser armazenadas em variaveis
var double = function (x) {
  return 2 * x;
};
```

- Higher Order Funcitions: Funções de ordem superior são funções que manipulam outras funções. Por exemplo, uma função pode receber outras funções como argumentos e / ou produzir uma função como seu valor de retorno.

```jsx
// Define two simple functions
var add_2 = function (x) {
  return x + 2;
};
var double = function (x) {
  return 2 * x;
};

// map is cool function that accepts 2 arguments:
//  func    the function to call
//  list    a array of values to call func on
var map = function (func, list) {
  var output = []; // output list
  for (idx in list) {
    output.push(func(list[idx]));
  }
  return output;
};

// We use map to apply a function to an entire list
// of inputs to "map" them to a list of corresponding outputs
map(add_2, [5, 6, 7]); // => [7, 8, 9]
map(double, [5, 6, 7]); // => [10, 12, 14]
```

---

### CONST VS LET VS VAR

- Const = é uma variável que não pode ser alterada ao longo do código
- Let = é uma variável comum que pode ser alterada.
- Var =

![JavaScript%2057f83c53ce37412d8efbe34e4d3c2184/Untitled.png](JavaScript%2057f83c53ce37412d8efbe34e4d3c2184/Untitled.png)

---

### DOM - DOCUMENT OBJECT  MODEL

Conjunto de objetos dentro do navegar, o DOM não funciona no node, apenas no navegador web:

```jsx
window.document.write('.......')
```

- Árvore DOM - Exemplo

    ![JavaScript%2057f83c53ce37412d8efbe34e4d3c2184/Untitled%201.png](JavaScript%2057f83c53ce37412d8efbe34e4d3c2184/Untitled%201.png)

---

### TIPOS DE SELEÇÃO

Podemos selecionar os elementos por: 

- TAG: `getElementsByTagName()` → retorna um array dos elementos pelo nome da tag passada (HTMLCollection)
- ID: `getElementById` → seleciona o elemento pelo id passado (element)
- Nome: `getElementsByName()` → seleciona o elemento pelo nome passado
- Classe: `getElementsByClassName()` → retorna um array dos elementos pelo nome da classe passada (HTMLCollection)
- Seletor:  `querySelector()` → retorna o elemento especificado  (element)
- Seletor: `querySelectorAll()` → retorna todos os seletores com o mesmo nome (Nodelist / quando for usar forEach)

---

### MANIPULANDO ESTILOS E CLASSES

Podemos manipular os estilos em linha:

`element.style.backgroundColor` = #FFFFFF

A manipulação também pode ser feita através do `classList` :

```jsx
const element = document.querySelector("body")

element.classList.add('nomedaclasse')
console.log(element.classList)
element.classList.remove('nomedaclasse')
```

---

### ADICIONANDO ELEMENTOS

Primeiro criamos o elemento com `createElement` , depois pegamos o ponto onde queremos adicionar com `querySelector` e usamos:

- append: cria depois do ultimo filho
- prepend: cria como primeiro filho
- Exemplo

    ```jsx
    //createElement
    const div = document.createElement('div')
    div.innerText = 'Olá Devs'

    //append ou prepend
    const body = document.querySelector('body')
    body.prepend(div)
    ```

Para adicionar em qualquer lugar usamos `insertBefore`:

elementoPai.insertBefore(elementoNovo, nóReferencia)

- Exemplo

    ```jsx
    //Add elemnetos
    const div = document.createElement('div')
    div.innerText = "Olá devs"

    //insertBerfore
    const body = document.querySelector('body')
    const script = body.querySelector('script')
    body.insertBefore(div, script)
    ```

### EVENTOS

Os eventos são um conjunto de ações que são realizadas em um determinado elemento da página web, seja um texto, imagem, div, etc. Os eventos podem sem aplicado em:

- Inline: dentro do arquivo html
- Exemplo

    ```html
    <!--Quando clicar na palavra interaja, ela muda para clicou-->

    <!DOCTYPE html>
    <html lang="pt-BR">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Eventos DOM</title>

        <style>
            div#area {
                background: green;
                color: white;
                width: 200px;
                height: 200px;
                line-height: 200px;
                text-align: center;
            }
        </style>

    </head>
    <body>
        <div id="area" onclick="clicar()">
            Interaja....
        </div>

        <script>
            function clicar() {
                var a = window.document.getElementById('area')
                a.innerText = 'Clicou!'
            }
        </script>
    </body>
    </html>
    ```

    Também é possível faz Inline a partir do Event Listener

    ```html
    <!DOCTYPE html>
    <html lang="pt-BR">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Eventos DOM</title>

        <style>
            div#area {
                background: green;
                color: white;
                width: 200px;
                height: 200px;
                line-height: 200px;
                text-align: center;
            }
        </style>

    </head>
    <body>
        <div id="area">
            Interaja....
        </div>

        <script>
            var a = window.document.getElementById('area')
            a.addEventListener('click', clicar)
            a.addEventListener('mouseenter', entrar)
            a.addEventListener('mouseout', sair)

            function clicar() {
                a.innerText = 'Clicou!'
                a.style.background = 'red'
            }
            function entrar() {
                a.innerText = 'Entrou!'
            }
            function sair() {
                a.innerText = 'Saiu!'
            }
        </script>
    </body>
    </html>
    ```

- Arquivo externo: através do `addEventListener:`

    elemento.addEventListener('nomeDoEvento', função)

- Exemplo

    ```jsx
    const h1 = document.querySelector('h1');

    h1.addEventListener('click', print)

    function print() {
    	console.log('print')
    }

    // pode ser h1.onclick mas não é recomendado pois
    // um sobreescrve o outro
    ```

Para descobrir as "propriedades" dos eventos podemos usar o `event` . O `event` já é uma "função" própria do JS, não é preciso criar.

- Exemplo

    ```jsx
    const input = document.querySelector('input')
    input.onkeydown = function(event) {
    	console.log(event)
    }
    ```

- Eventos de teclado

    ```jsx
    const input = document.querySelector('input')

    input.onkeydown = function() {
    	console.log('rodei')
    }

    //onkeyup, onkeypress, onkeydown
    ```

---

### MANIPULANDO CONTEÚDOS

- textContent

    Seleciona o texto:

    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Meu blog - discovery</title>
    </head>
    <body>
        <h1>Meu Blog</h1>

        <script src="apagardepois.js"></script>
    </body>
    </html>
    ```

    ```jsx
    //selecionando
    const element = document.querySector('h1')

    //alterando o conteudo
    element.textContent = "Olá Devs"
    ```

- innerText

    Troca o texto interno

- innerHTML

    Trocar o conteúdo HTML interno 

    ```jsx
    const element = document.querySelector('h1')
    element.innerHTML = "Olá <strong>Devs</strong>!!"
    ```

- Value

    Serve para manipular o valo de um input

- Atributos
    - Podemos adicionar:  `.setAttribute()`
    - Podemos pegar: `.getAttribute()`
    - Podemos remover: `.removeAttribute()`

---

### NAVEGANDO PELOS ELEMENTOS

- Para navegar pelos elementos *pai :* `parentElement`  ou   `parentNode`
- Para navegar entre os *filhos:*
    - `.children` - não conta os espaços vazios (HTMLColletion)
    - `.childNodes` - conta os espaços vazios (Nodelist)
    - `.firstChild` - conta o espaço vazio e pega o primeiro
    - `.firstElementChild` - não conta o espaço vazio e pega o ultimo
    - `.lastChild` e `.lastElementChild` - pega o último
- Para navegar entre os irmãos:
    - `.nextSibling` - conta o espaço
    - `.nextElementSibling` - não conta o espaço

---

### ORIENTADO A OBJETO

A idéia básica da OOP é que usamos objetos para modelar coisas do mundo real que queremos representar dentro de nossos programas, e / ou fornecer uma maneira simples de acessar funcionalidades que de outra forma seriam difíceis ou impossíveis de usar.

Os objetos podem conter dados e códigos relacionados, que representam informações sobre o que você está tentando modelar e a funcionalidade ou o comportamento que você deseja ter. Dados de objeto (e muitas vezes, funções também) podem ser armazenados ordenadamente (a palavra oficial é **encapsulados**) dentro de um pacote de objetos (que pode ser dado um nome específico para se referir, que é às vezes chamado de **namespace**), tornando fácil de estruturar e acessar; objetos também são comumente usados como armazenamentos de dados que podem ser facilmente enviados pela rede.

---

### CLASSES

As classe são usadas para evitar a repetição de declaração de variáveis. 

- Exemplo

    ```jsx
    // Declaração das propriedades dos clientes atraves de classes //
    class Cliente{
        nome;
        cpf;
        agencia;
        saldo;
        rg;
    }

    // Criando um novos clientes //
    const cliente1 = new Cliente();
    const cliente2 = new Cliente();

    // Dados dos clientes //
    cliente1.nome = "Ricardo";
    cliente1.cpf = 11122233309;
    cliente1.agencia = 1001;
    cliente1.saldo = 0;
    cliente1.rg = 123456789;

    cliente2.nome = "Alice";
    cliente2.cpf = 88822233309;
    cliente2.agencia = 1001;
    cliente2.saldo = 0;
    cliente2.rg = 987654321;
    ```

    Nesse caso, cada cliente criado é um objeto e a classe é o "molde" para a criação desses clientes.

As classes podem ser exportadas de outros arquivos e devem começar com letra maiúscula (módulos)

- Exemplo

    ```jsx
    // Arquivo Pricipal - Imports //
    import { NomeClasse1 } from "./NomeClasse1";
    import { NomeClasse2 } from "./NomeClasse2";
    ```

    ```jsx
    // Arquivo Classe //
    export class NomeClasse1{
        atributo1;
        atributo2;
    }

    export class NomeClasse2{
        atributo1;
        atributo2;
    }
    ```

---

### ATRIBUTOS PRIVADOS

Protege a variável para que a mesma não possa ser alterada. A variável deve ser iniciada com #.

- Exemplo

    ```jsx
    // Saldo está protegido e não pode ser alterado
    class Cliente{
        nome;
        cpf;
    }

    class ContaCorrente{
        agencia;
        #saldo;

        sacar(valor){
            if(this._saldo >= valor){
                this._saldo -= valor;
            }
        }

        depositar(valor){
            if(valor > 0){
                this._saldo += valor;
            }
        }
    }
    ```

---

### GET E SET

O getter, com a sintaxe get é associado a uma função que será chamada quando a propriedade em questão for acessada e solicitada de forma dinâmica. É possível utilizá-la para retornar o status de uma variável interna, sem utilizar métodos de forma explícita. 

Alguns pontos importantes a serem destacados para o uso de getters são:

- Pode ter um identificador do tipo numérico ou string.
- Não deve ter nenhum parâmetro.
- Não pode ser utilizado mais de um getter para uma mesma propriedade, assim como não pode haver uma propriedade comum com o mesmo nome do getter.

Geralmente usados junto com os getters, os setters são utilizados para definirem valores para uma propriedade específica.

Alguns pontos importantes a serem destacados para o uso de setters são:

- Pode ter um identificador do tipo numérico ou string.
- Deve ter exatamente um parâmetro.
- Não pode ter a mesma nomenclatura para propriedade e função.

### USO DO THIS

O this é usado para referenciar o "campo genérico" dentro de uma função. Exemplo:

```jsx
class ContaCorrente{
    agencia;
    saldo;

    //definindo funções = metodos = comportamentos
    sacar(valor){
        if(this.saldo >= valor){   
            this.saldo -= valor;
        }
    }
}
//representa a conta corrente de quealquer cliente
```

---

### CONSTRUCTOR

O construtor é um método especial para criar e inicializar um objeto criado a partir de uma classe.

- Exemplo

    ```jsx
    // Declaração das propriedades dos clientes e da conta atraves de classes //
    export class Cliente{
        nome;
        _cpf;

        get cpf(){
            return this._cpf;
        }

        constructor(nome, cpf){
            this.nome = nome;
            this._cpf = cpf;
        }
    }
    ```

    ```jsx
    // Imports //
    import { Cliente } from "./Cliente";
    import { ContaCorrente } from "./ContaCorrente";

    // Criando novos clientes e seus dados //
    const cliente1 = new Cliente("Ricardo", 11122233309);
    ```

---

---

### RESUMO SINTAXES

[Untitled](https://www.notion.so/cf0d716b49d941238b6743f3d384bf7f)