Problema: Dentro da linguagem de programação C/C++ temos o problema de que inteiros e mesmo inteiros de 64 bits tem uma representação limitada. Veja que elas tornam o codificar muito mais simples, pois não precisamos nos preocupar com a implementação da adição, multiplicação, divisão e subtração. 

Veja que problemas que exigem a utilização de números bem grandes devem ser lidados de outra forma. Uma maneira de fazer isso é através do **vetor de dígitos**. 

```C++
#define MAXDIGITS 100
const int PLUS = 1;
const int MINUS = -1;

struct BigNum{
	char digits[MAXDIGITS];
	int signBit;
	int lastDigit;
};
```

Veja que aqui, por questão de conveniência, iremos usar que o índice zero dentro do array será equivalente ao dígito menos significativo.