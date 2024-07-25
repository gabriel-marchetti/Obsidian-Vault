O método mais simples que me vem a cabeça é o método da bissecção. Primeiro porque ele foi o primeiro método numérico que eu aprendi! Segundo, porque a bagagem dele não recorre a nenhum ferramentário extraordinário. De modo que, um aluno fazendo cálculo 1 (ou até antes disso) poderá ter uma grande intuição do método! O método possui diversos pontos negativos, contudo é um ótimo começo para o estudo de métodos numéricos.

### Problemas
1. O método consiste de um método lento.
2. Apresenta bastante erro numérico.
3. Existem métodos mais refinados.

Alguns métodos que ainda vamos ver são [[Descartes Rule Of Sign's]], [[Sturm's Theorem]] e o [[Budan's Theorem]]. Basicamente o que esses métodos se propõem é em extender o método da bissecção em algoritmos mais eficientes, de modo que todas as raízes são encontradas! Assim outro problema que ficará claro é que o método da bissecção nos possibilita encontrar um única raiz a não ser que usemos algumas modificações e estratégias para burlar isto. Contudo, vamos desenvolver inicialmente a proposta mais simples.

Suponhamos inicialmente que $f(x$) seja uma função contínua. Além disso ela está determinada entre os intervalos $[a,b]$ se tivermos determinados os sinais de os valores de $f(a)$ e $f(b)$, de modo que  $sign(f(a)) \neq sign(f(b))$ ou seja os sinais de $f(a)$ e de $f(b)$ são diferentes. Então haverá uma raiz entre eles! Notemos que a suposição de que $f( \cdot )$  seja contínua é extremamente importante, porque somente nesse caso haverá uma raiz. 

Também vamos lembrar de um teorema de cálculo 1. O teorema primordial aqui é o [[Intermediate value theorem]] 