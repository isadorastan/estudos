### Estudando teorias 🧠

Neste repositório deixarei por escrito algumas questões teóricas que são chatas, porém necessárias para a evolução profissional 🤪

### JS 

#### Hoisting

Hoisting é o içamento de funções e variáveis para o topo do código, declarando variáveis e funções em memória e permitindo que você use uma função/variável antes mesmo de declara-las.

    sayHello();
    // a função foi chamada antes de ser declarada
    
    functionSayHello() {
	    console.log("Say Hello");
	}

O mesmo acontece com variáveis, as quais podem ser inicializadas antes de serem declaradas. Porém, o js eleva somente a declaração não a inicialização.

      console.log(num); // undefined -> nesse caso num é undefined porque só foi declarada
      num = 6;
      console.log(num); // 6 -> agora num já foi inicializada
      var num;
      
#### Scope
Escopo é a acessibilidade de objetos, variáveis e funções em diferentes partes do código.

- Escopo Global
	- Uma variável global é definida quando declaramos uma variável fora de qualquer função, assim ela torna **acessível a qualquer parte** da nossa aplicação ou site, podendo ser lida e alterada.

- Escopo Local
	- Uma variável se torna local quando ela é declarada dentro de uma função, de tal maneira a qual ela somente estará **acessível dentro dessa função**.
	
- Escopo de bloco
	- Não existia no JS escopo de bloco. Ou seja, for whiles e ifs não tinham escopo próprio. Porém com o ECMAScript 6 foi possível criar escopos de bloco usando as variáveis **let** e **const**, que são **acessíveis somente dentro do bloco.**



