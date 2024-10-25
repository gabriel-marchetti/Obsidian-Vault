No sentido mais usual de variáveis dizemos que variáveis são nomes que seguram valores que mudam conforme o tempo. Contudo, em um termo mais técnico podemos dizer que variáveis são nomes de posições de memória. 

Nesse sentido, podemos pensar na memória principal do programa como sendo um grande vetor de bytes. Assim como em um vetor, temos que cada posição de memória tem um índice! Sendo limitado ao índice máximo que seu computador pode representar. Por exemplo, um computador com uma CPU de 32-bits pode representar no máximo $2^{32}$ posições de memória.

Veja aqui que há um problema especialmente limitante para os computadores se adotarmos uma CPU que tenha 32-bits. Temos a limitação de que a memória principal de tal CPU pode ter no máximo 4 GB, que nos padrões de hoje é pouca memória. Mais especificamente temos uma memória de 4_294_967_296 bytes. Veja que uma CPU de 64-bits possuirá $2^{32}$ vezes esse valor.

Deixando a divagação de lado, veja que cada índice dessa abstração em array da memória principal é única e usualmente dizemos que esse é o endereço da memória, outro nome usual para isso é ponteiro. Veja que a definição de um nome para uma variável nada mais nos diz que a posição de memória X espera receber um valor característico.

## Variable names
1. O nome de uma variável não deve começar com um número.
2. O nome de uma variável não deve começar com dois "underscores".
3. O nome de uma variável não deve começar com um "underscore" e uma letra maiúscula.


## Ternary Operator
Dentro do C existe uma operação muito útil que reduz o código, tal operação é conhecida como operação ternária e substitui um "if".

```C

y += (x > 10) ? 17 : 37;

```

Leia como: se (x > 10) for satisfeita, então some 17, senão some 37.

Uso útil:

```

```