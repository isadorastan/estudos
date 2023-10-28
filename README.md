### Estudando teorias 🧠

Neste repositório deixarei por escrito algumas questões teóricas que são chatas, porém necessárias para a evolução profissional 🤪

### JS 
- [Como funciona o JS](#how-js-works)
- [O que é o JS](#what-is-js)
- [Operadores](#operators)
- [Hoisting](#hosting)
- [Scope](#scope)
- [Nested Scopes](#nested-scopes)
- [Variables](#variables)
- [ES6 Features](#es6-features)
- [Pure Functions](#pure-functions)
- [Closure](#closure)
- [Currying](#currying)
- [Higher-Order Functions](#higher-order-functions)

#### <a name="how-js-works"></a> Como funciona o JS
O google chrome usa a engine v8 (open source escrita em c++) . A engine v8 serve para interpretar um código javascript. 
A v8 foi projetada para aumentar a perfomance de execução do JS dentro de navegadores, ele compila código JS em código de maquina ao invés de usar um interpretador. Ele compila de js para código de máquina em tempo de execução, implementando um compilador JIT (just in time).

```JS => c++ => Assembly => Machine Code ```

#### <a name="what-is-js"></a> O que é o JS
Javascript é como nós chamamos a linguaguem (mas isso é o trademark da Oracle), o nome oficial da linguagem é ECMAScript (ES) é a abreviação. 

```ES6 === ECMAScript 6 === ES2015```, é simplesmente a versão *mais nova da linguagem (entre aspas)*.

 O que aconteceu é que o ES5, não é de 2014.. mas sim de 1999. Isso mesmo, ficamos 16 anos sem updates. Basicamente porque não era tão bom e existiam algumas alternativas, a mais famosa delas: o Flash. Em 2008 o google Chrome foi lançado, e aclamado por sua perfomance na execução de javascript, o que iniciou uma guerra pelo desenvolvimento de interpretadores cada vez mais rápidos, o que deixou o chrome para trás. Até que foi lançado em 2013, a nova versão do chrome usando a V8, tornando-o novamente o mais rápido na execução de JS. Dois anos após.. tivemos o ES6.

Suporte ES:
- O  **ECMAScript 3**  é totalmente  **suportado**  em  **todos os navegadores**.
- O  **ECMAScript 5 (2009)**  é totalmente  **suportado**  em  **todos os navegadores modernos**  .  **Observação**: O  **Internet Explorer 9 não suporta ECMAScript 5**  `"use strict"`.
- O  **ECMAScript 6 (ECMAScript 2015)**  é totalmente  **suportado**  em  **todos os navegadores modernos, menos no Internet Explorer.**
- O  **ECMAScript 7 (ECMAScript 2016)**  é suportado  **apenas no Chrome e Opera.**

**NOTA:**  Observe sempre as  **versões do browser**  e quais  **métodos**  são  **compatíveis**  no  **mesmo**.

**Se nem todos os browsers suportam o ES6 como fazemos?**
por isso usamos transpilers como o BABEL. Ele transforma seu código ES6 em ES5 (que a maioria dos browsers dá suporte)

fontes:
- [https://medium.com/@matheusml/o-guia-do-es6-tudo-que-voc%C3%AA-precisa-saber-8c287876325f](https://medium.com/@matheusml/o-guia-do-es6-tudo-que-voc%C3%AA-precisa-saber-8c287876325f)
- [https://pt.wikipedia.org/wiki/Interpretador_de_JavaScript](https://pt.wikipedia.org/wiki/Interpretador_de_JavaScript)
- [https://pt.stackoverflow.com/questions/383174/o-ecmascript-6-%C3%A9-suportado-pelos-browsers-atuais](https://pt.stackoverflow.com/questions/383174/o-ecmascript-6-%C3%A9-suportado-pelos-browsers-atuais)

#### <a name="operators"></a> Operadores

## Operadores de comparação
- Igual `==`  
- Não igual `!=`
- Estritamente igual `===`
- Estritamente não igual `!==`
- Maior que `>` e maior igual 	que `>=`
- Menor que `<` e menor igual que `<=`

```javascript
const maioridade = 18;
const idade = 16;
console.log(idade >= maioridade); // false

1 == '1' // true
1 === '1' // false

1 != '1' // true
1 !== '1' // false
```

## Operadores aritméticos
### Módulo `%`
```javascript
// resto da divisão
const result = 12%5 // result = 2
```
### Incremento `++`
```javascript
// prefixado
let x = 3;
++x // retorna 4

// posfixado
let x = 3
x++ // retorna 3 depois define x como 4
```
### Decremento `--`
```javascript
// prefixado
let x = 3;
--x // retorna 2

// posfixado
let x = 3
x-- // retorna 2 depois define x como 2
```
### Negação `-`
```javascript
let x = 3;
-x // retorna -3
```
### Adição `+`
```javascript
// converte um operando em número, sempre que possível
+"3" // retorna 3
+true // retorna 1
```
### Exponencial `**`
```javascript
 let x = 2**3 // retorna 8
```

## Operadores de atribuição
### Atribuição
```javascript
	x = y
```
 ### Atribuição matemáticos
```javascript
	x += y // x = x + y (adição)
	x -= y // x = x - y (subtração)
	x *= y // x = x * y (multiplicação)
	x /= y // x = x / y (divisão)
	x %= y // x = x % y (resto)
	x **= y // x = x ** y (exponencial)
```
## Operadores lógicos
### `!` Operador lógico NÃO (NOT)
Se aplicado a um valor não booleano, primeiro converte em booleano e depois torna ele o contrário.
```javascript
let required = true;
console.log(!required) // false	
```

### `!!` Negação dupla (converter para boolean)
```javascript
let x = 10;
console.log(!!x) // true	
```
### `||` Operador lógico OU (OR)
Retorna false somente se os dois valores forem falsos, se não, retorna true;

| `a`| `b` |`a ou b` |
|---|----|----|
|true |true | true|
|true |false | true|
|false |true | true|
|false |false | false|

```javascript
let result = a || b;  // Se A for true, retorna A.
                      // Caso contrário, retorna B
				
```
### `&&` Operador lógico E (AND)
Retorna `true` somente se os dois valores forem verdadeiros

| `a`| `b` |`a && b` |
|---|----|----|
|true |true | true|
|true |false | false|
|false |true | false|
|false |false | false|

```javascript
let result = a && b; // Se A for true, retorna B.
// Caso contrário, retorna A
```
### Curto-circuito

O operador `&&` está em curto-circuito, ou seja, avalia o segundo valor, apenas se o primeiro não for o suficiente para determinar o valor da expressão.
- Avalia valores da esquerda p/ direita
- Converte em booleano, se for `false`, interrompe a validação e retorna o valor 'falso'
- Se todos forem `true`, retorna o último valor
- Em outras palavras, o operador `&&` retorna o primeiro valor falso ou o último verdadeiro.
```javascript
let a = 10;
let b = 0;
let c = 'a''
let result = A && B && C; // 10 && 0 && 'a'
                          // true
                          // true && false -> INTERROMPE e retorna 0 

let result2 = 'a' && 'b'&& 'c' // todos são true, retorna 'c' (o último)

//como usar no dia a dia?
required && validateFunction() // se required for true, vai chamar a função
```

O operador `||` está em curto-circuito, ou seja, se o primeiro valor avaliado for `true` o operador não vai avaliar o segundo valor.
- Avalia valores da esquerda p/ direita
- Converte em booleano, se for `true`, interrompe a validação e retorna o valor
- Se todos forem `false`, retorna o último valor 
- Em outras palavras, o operador `||` retorna o primeiro valor `true` ou o último valor.
```javascript
let a = 10;
let b = 0;
let c = 'a''
let result = A || B || C; // 10 || 0 || 'a'
                          // true -> INTERROMPE E RETORNA 10 
```

### Precedência lógica do operador
Quando usamos vários operadores em uma mesma expressão, o JS avalia em uma ordem específica.

- `* / %` multiplicação, divisão, resto
- `+ - ` adição e subtração
- `< <= > >=` relacional
- `== != === !==` igualdade
- `!` não
- `&&` e
- `||` ou

```javascript
let result = (true || false) && !false; // Retorna true
           // true && true
           // true
let result = true || false && !false; // Retorna true
          // true || false && true -> primeiro o !
          // true || false         -> segundo o &&
          // true 
```


#### <a name="hoisting"></a> Hoisting
Hoisting é o içamento de funções e variáveis para o topo do código, isso declara as variáveis e funções em memória e permite que você use uma função/variável antes mesmo de declara-la.
```javascript
sayHello();
// a função foi chamada antes de ser declarada
    
functionSayHello() {
    console.log("Say Hello");
}
```
O mesmo é acontece para variáveis, as quais podem ser inicializadas antes de serem declaradas. Porém, o js eleva somente a declaração não a inicialização.
```javascript 
console.log(num); // undefined -> nesse caso num é undefined porque só foi declarada
num = 6;
console.log(num); // 6 -> agora num já foi inicializada
var num;
```

####  <a name="scope"></a>Scope
Escopo é a acessibilidade de objetos, variáveis e funções em diferentes partes do código.

- Escopo Global
	- Uma variável global é definida quando declaramos uma variável fora de qualquer função, assim ela torna **acessível a qualquer parte** da nossa aplicação ou site, podendo ser lida e alterada.

- Escopo Local
	- Uma variável se torna local quando ela é declarada dentro de uma função, de tal maneira a qual ela somente estará **acessível dentro dessa função**.
	
- Escopo de bloco
	- Não existia no JS escopo de bloco. Ou seja, for whiles e ifs não tinham escopo próprio. Porém com o ECMAScript 6 foi possível criar escopos de bloco usando as variáveis **let** e **const**, que são **acessíveis somente dentro do bloco.**

#### <a name="nested-scopes"></a> Nested Scopes

Todo o escopo é fechado para acessos externos, de forma que escopos superiores não conseguem acessar escopos internos, mas o contrário é permitido.

``` javascript 
function foo() {
    function bar() {
    
    }
}
```

Quando criamos outra função dentro da função foo, estamos colocando outra caixa dentro do escopo da função, criando o que é chamado de “nested scopes”, ou escopos aninhados.


#### <a name="variables"></a> Variables (var, let e const)

![enter image description here](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/1ee22f2b-7f95-48ac-890a-04e836a28492/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5/20200801/us-west-2/s3/aws4_request&X-Amz-Date=20200801T182119Z&X-Amz-Expires=86400&X-Amz-Signature=2f0cb6811c8cba5fd0103919a5856e514fdccdc8027343f324602c888251dd38&X-Amz-SignedHeaders=host&response-content-disposition=filename%20=%22Untitled.png%22)

- Var 
	-    é içada
	-   tem escopo abrangente → se for declarada dentro de um bloco → vaza do escopo
	-   escopo global e função → n tem escopo de bloco
	- Praticamente não são mais usadas em aplicações modernas devidos aos problemas de escopo → **substituídas por const e lets**
  
```javascript
function foo (a) {
  var name = 'Lucas'
  
  function bar () {
    var age = 23
    console.log(name) // Luca
    console.log(age) // 23
  }
  
  bar() // Lucas - 23
  console.log(name) // Lucas
  console.log(age) // age is not defined
}
```

```javascript
if(true) {
    var global = 2; // vaza de dentro do bloco
}

function teste() {
    var global = 4;
    console.log(global); //4
}

console.log(global); //2 -> acessa a que vazou do if
``` 

- Let e Const
	-   Tem escopo de **bloco** e de função
	-  Sofrem hoisting (são elevadas) para o topo do bloco que foram definidas → porém não é atribuido o valor de undefined como acontece com var  → continuam não inicializadas e dão erro caso sejam chamadas antes de suas declarações.
	- A grande diferença entre as duas é que consts não podem ser reatribuídas enquanto lets sim.

```javascript
function name() {
	console.log(name); // ❌ retorna erro porque ainda não foi inicializada
	let name = 'isadora';
	console.log(name); // 👍🏼 isadora
	name = 'isadora 2'; // 👍🏼 pode ser reatruída
}

const num = 6;
num = 8; // ❌ Não pode ser reatribuída porque é const

```
	
#### <a name="es6-features"></a> ES6 Features

- Declaração de variáveis
- Default Parameters
- Rest parameters
- Programação funcional => arrow functions
- Destructing
- Classes (constructor, get/setters, herança (extends))
- Es6 Modules (import, export)

fonte: [https://medium.com/@matheusml/o-guia-do-es6-tudo-que-voc%C3%AA-precisa-saber-8c287876325f](https://medium.com/@matheusml/o-guia-do-es6-tudo-que-voc%C3%AA-precisa-saber-8c287876325f)

#### <a name="pure-functions"></a> Pure Functions
- Dada a mesma entrada, vai sempre retornar a mesma saída
- Não produz nenhum efeito colateral
```javascript
functions pureFunction(a,b) {
	return a + b;
} 
pureFunction(1,2) // retorna 3
 ```
 - Retorna sempre o mesmo valor baseado na entrada e não manipula nenhuma variável de fora.
 - Porque usar?
	 - Mais fáceis de implementar e testar
	 - Código mais limpo, prático e de simples manutenção
 
#### <a name="currying"></a> Currying
```Currying é o nome dado à técnica de dividimos uma função que recebe vários argumentos numa série de funções cada uma lidando com **um** argumento da função inicial.```

- Forma de injetar os parametros de forma parcial. 
- É uma função normal
- Faz parte de programação funcional
- Transforma uma função com múltiplos argumentos em uma sequencia de nested functions (função aninhada). Ela retorna uma função que espera os próximos argumentos.

```javascript
function somap(a) {
    return function(b) {
        return a+b
    }
}

// Uso:
var somadois = somap(2);
somadois(3); // 5
 ```
também podemos executa-lá de uma vez fazendo:
```somap(2)(3) // retorna 5 ```

também pode ser escrita usando arrow functions: 
```javascript
const myFunction = valor1 => valor2 => valor3 => {
	return valor1 + valor2 + valor3;
}

console.log(myFunction(1)) // retorna a função esperando o segundo parametro
console.log(myFunction(2)(4)(3)) // retorna 8
```

#### <a name="higher-order-functions"></a> Higher-Order Functions
- É uma função que **recebe como parâmetro** outra função e/ou que **retorna** uma função
- Ex: map, reduce, filter..
 
```javascript
// calculate recebe como parametro uma função
// calculate retorna uma função
// Higher-Order function
var calculate = function(fn, x, y) {
	return fn(x, y);
};

var sum = function(x, y) {
	return x + y;
};

var mult = function(x, y) {
	return x * y;
};

calculate(sum, 2, 5); // 7
calculate(mult, 2, 5); // 10
 ```
usando ES6:
```javascript
const calculate = (fn, x, y) => fn(x,y);
const sum = (x, y) => x + y;
const mult = (x, y) => x * y;
calculate(sum, 2, 5); // 7
calculate(mult, 2, 5); // 10
 ```

#### <a name="closure"></a> Closure
- Closure é a forma de fazer com que as variáveis dentro de uma função sejam **privadas** e **persistentes**.
- Se refere à forma como funções definidas dentro de um "contexto léxico" (i.e. o corpo de uma função, um bloco, um arquivo fonte) acessam variáveis definidas nesse contexto.

```javascript
function pai(){  
   var x = 1;  
   function filho(){  
	  console.log(x);  
	  x++;  
   }  
   return filho;  
}  
  
var contador = pai();  
contador(); // 1  
contador(); // 2  
contador(); // 3
```
```A função filho possui uma referência ao escopo da função pai, e a essa referência nós damos o nome de closure.```

- Módulos são estruturas de código que fazem bom uso das _closures_, vamos a um exemplo que apresenta bem seu funcionamento:
```javascript
 function ModuloMatematico() {       
    var x = 0;      
    function somaUm() {  
        x++;          
        console.log(x);       
    }
    function subtraiUm() {           
        x--;  
        console.log(x);       
    }
	return {           
        somaUm: somaUm,           
        subtraiUm: subtraiUm       
    };   
}
var teste = ModuloMatematico();    
teste.somaUm();     // 1   
teste.somaUm();     // 2  
teste.somaUm();     // 3  
teste.subtraiUm();  // 2
```
Nesse exemplo, não seria possível acessar diretamente X, porém usando closures é possível fazer isso.
