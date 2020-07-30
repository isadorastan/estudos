### Estudando teorias 🧠

Neste repositório deixarei por escrito algumas questões teóricas que são chatas, porém necessárias para a evolução profissional 🤪

### JS 

#### Hoisting
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

