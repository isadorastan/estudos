### Estudando teorias 🧠

Neste repositório deixarei por escrito algumas questões teóricas que são chatas, porém necessárias para a evolução profissional 🤪

### JS 
- [Hoisting](#hosting)
- [Scope](#scope)
- [Nested Scopes](#nested-scopes)
- [Variables (let, const, var) ](#variables)


#### <a name="hoisting"></a> Hoisting
Hoisting é o içamento de funções e variáveis para o topo do código, isso declara as variáveis e funções em memória e permite que você use uma função/variável antes mesmo de declara-la.

    sayHello();
    // a função foi chamada antes de ser declarada
    
    functionSayHello() {
	    console.log("Say Hello");
	}

O mesmo é acontece para variáveis, as quais podem ser inicializadas antes de serem declaradas. Porém, o js eleva somente a declaração não a inicialização.

      console.log(num); // undefined -> nesse caso num é undefined porque só foi declarada
      num = 6;
      console.log(num); // 6 -> agora num já foi inicializada
      var num;


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

    function foo() {
	    function bar() {
	    
	    }
	}

Quando criamos outra função dentro da função foo, estamos colocando outra caixa dentro do escopo da função, criando o que é chamado de “nested scopes”, ou escopos aninhados.


#### <a name="variables"></a> Variables (var, let e const)

![enter image description here](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/1ee22f2b-7f95-48ac-890a-04e836a28492/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5/20200801/us-west-2/s3/aws4_request&X-Amz-Date=20200801T182119Z&X-Amz-Expires=86400&X-Amz-Signature=2f0cb6811c8cba5fd0103919a5856e514fdccdc8027343f324602c888251dd38&X-Amz-SignedHeaders=host&response-content-disposition=filename%20=%22Untitled.png%22)


- Var 
	-   É içada
	-   Tem escopo abrangente → se for declarada dentro de um bloco → vaza do escopo
	-   Escopo global e função → n tem escopo de bloco
	-   Praticamente não são mais usadas em aplicações modernas devidos aos problemas de escopo → **substituídas por const e lets**
  
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
	-  Tem escopo de **bloco** e de função
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

