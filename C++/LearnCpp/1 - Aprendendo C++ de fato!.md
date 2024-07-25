Programas de computador são arquivos que dão um passo-a-passo para o computador. Dentro desse passo-a-passo existem os Statements que nada mais são que tarefas que o programa deve realizar. A maior parte dos Statements feitos pelo C++ terminam com um ";". Desse modo sempre que virmos um ";", provavelmente teremos algum comando ou ação sendo realizada. 

std::cout : 
	std: chama  a preprocessor standard
	cout: character output

<< : 
	Nos possibilita enviar números e letras para o console output.

Quiz:

1. What is a Statement?
Um Statement é uma "sentença" que é traduzida para o computador como uma ação.
2. What is a function?
Uma função é um conjunto de "sentenças" que é condensada num bloco de código. Essas "sentenças" são executadas sequencialmente.
3. What is the name of the function which all programs should have?
O nome dessa função é main.

Exemplos de comentários. Nesse caso devemos analisar o contexto do comentário, não devemos explicar o que os comandos estão fazendo isso é muito contraprodutivo para a pessoa que está lendo. Devemos fazer comentários que traduzem contextos dos programas, por exemplo:
Comentário **RUIM**
```C++
// sight recebe zero.
sight = 0;
```
Comentário **BOM**
```C++
// sight recebe zero, pois o jogador bebeu uma bebida estranha.
sight = 0;
```

Assim como, podemos explicar algumas contas:
Comentário **BOM**
```C++
// usamos 2 pois este item é comprado aos pares nessa loja.
price = 2 * storePrice * quantity;
```

Para o caso de aplicar alguns método:
* Usamos uma lista ligada ao invés de um array, pois lista ligadas conseguem adicionar mais rapidamente um elemento do que um array.
* Usamos o Método de Newton para esse problema, pois não há método determinístico para resolver essa equação.

Para escrever um comentário sempre podemos nos perguntar:
* O quê?
* Como?
* Por quê?

É importante ter noção de que os códigos usados nesse "curso" são demonstrativos, portanto, muitos comentários são comentários ruins. Acho importante notar os comentários ruins.

Para comentar um trecho de código é viável que você use os seguintes comandos dentro do VS Code:
	ctrl-k-c : Comenta as linhas selecionadas.
	ctrl-k-u : Descomenta as linhas selecionadas.

Do modo usual que programamos temos a memória que é executada pelo programa. Cada variável é estocada em um espaço de memória. Contudo agora podemos entrar em um outro paradigma de programação. O paradigma de objetos, o objeto é em geral um espaço da memória que reservamos para o dado e suas propriedades inerentes. Como o compilador e a memória trabalham para suportar esse objeto é um mistério por enquanto.

## Inicialização de variáveis.
No C++ temos diversos tipos de inicialização de variáveis, isto porque alguns desses tipos serão mais eficientes para inicializar variáveis complexas.

```C++
#include <iostream>

int main()
{
	int a;         // (1)
	int b = 5;     // (2)
	int c( 5 );    // (3)

	// Preferível
	int d = { 5 }; // (4)
	int e { 5 };   // (5)
	int f {};      // (6)
}
```

Aqui temos diversos tipos de inicialização.
* (1): É um método usual de inicializar variáveis sem definir um valor. Isso é uma má prática de programação, uma vez que é preferível definir o tipo nulo para essas variáveis.
* (2): Esse aqui é chamado de Copy Initialization apesar de ser o modo mais comum do C aqui não é muito utilizada, uma vez que é menos eficiente que os outros métodos de inicialização.
* (3): Foi usada para tornar a inicialização de alguns objetos mais eficientes, entretanto foi entrada em desuso por outras normas e novidades da linguagem. Seu desuso também é função de ser interpretada como uma função em alguns casos...
* (4), (5) e (6): São os métodos usuais de inicialização em C++. É conhecida como List Initialization. Esse método é muito bom pois impossibilita estreitamento de conversão e dará um erro caso não seja possível alocar esse tipo de valor dentro da variável.

O {} também é conhecido como empty initialization.

### Pontos para ficar atento.
Uma frase foi destacada pelo autor que é "Você primeiro precisa saber fazer um programa para saber como você deveria tê-lo implementado da primeira vez". Desse modo, é muito mais importante tentar realizar o seu código sem se preocupar muito com a otimização prematura... Assim como outros fatores devem ser considerados como manutenibilidade que é muitas vezes mais importante para grandes códigos. Assim, quando terminamos um programa, muitas vezes vale a pena voltar e ver como poderíamos ter otimizado ele melhor, como torná-lo mais legível e por ai vai.