### Estudando teorias 🧠

Neste repositório deixarei por escrito algumas questões teóricas que são chatas, porém necessárias para a evolução profissional 🤪

### JS 
- [Como funciona o JS](#how-js-works)
- [O que é o JS](#what-is-js)
- [Hoisting](#hosting)
- [Scope](#scope)
- [Nested Scopes](#nested-scopes)
- [Variables](#variables)
- [ES6 Features](#es6-features)

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
por isso isamos transpilers como o BABEL. Ele transforma seu código ES6 em ES5 (que a maioria dos browsers dá suporte)

fontes:
[https://medium.com/@matheusml/o-guia-do-es6-tudo-que-voc%C3%AA-precisa-saber-8c287876325f](https://medium.com/@matheusml/o-guia-do-es6-tudo-que-voc%C3%AA-precisa-saber-8c287876325f)
[https://pt.wikipedia.org/wiki/Interpretador_de_JavaScript](https://pt.wikipedia.org/wiki/Interpretador_de_JavaScript)
[https://pt.stackoverflow.com/questions/383174/o-ecmascript-6-%C3%A9-suportado-pelos-browsers-atuais](https://pt.stackoverflow.com/questions/383174/o-ecmascript-6-%C3%A9-suportado-pelos-browsers-atuais)

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
