### Despacho Múltiplo
É uma característica de linguagens orientada a objetos onde um método (ou função) pode ser dinamicamente modificada com mais de método. Em outras palavras, podemos especificar o método de uma função ou torná-la mais geral.

g ( generic function with 1 method )
g ( generic function with 2 methods )

E por ai vai.

```julia
>> g(x::Vector{Int}, y::Vector{Int}) = x - y
>> g(x,y) = x + y
```

Se chamarmos o método com argumentos de vetor de inteiros ele fará um processo diferente do que de um vetor de ponto flutuante.

Pacote Octavian! -> Tem algumas implementações 
@benchmark.

Fazer uma estrutura dentro do Julia. Base fazer:
```julia
>> struct MyNumber
	x::Float64
	y::Float64
	end
```

Isso pode ser entendido como uma implementação de um número complexo, desse modo precisamos definir a multiplicação.

```julia
*(x::MyNumber, y::MyNumber) = MyNumber(x.x*y.x, x.y*y.y)
+(x::MyNumber, y::MyNumber) = MyNumber(x.x+y.x, y.x+y.y)
```

### Coisas Práticas
-> O Benchmarking é muito útil dentro do Julia. Além disso, como é uma linguagem que funciona com o particionamento do código em métodos que podem ser otimizados por compilação. Então o fato de podermos ter acesso muito fácil ao benchmarking faz com que tenhamos noção de qual função está desacelerando nosso código, de modo que podemos otimizar partes específicas do nosso código. 

-> A parte de criação de bibliotecas é extremamente útil! De modo que em poucos minutos podemos atualizar um código e postá-lo dentro do GitHub. De modo que, podemos acessar dentro de um Linux, Windows ou até mesmo IOS. Dentro do link: https://m3g.github.io/JuliaNotes.jl/stable/new_package/ podemos ver mais detalhes sobre isso! 

#### Algumas observações.
-> @turbo : vetoriza as operações
-> @tturbo  : vetoriza as operações e roda em paralelo
-> eachindex(x) : função que parece ser boa.
-> CUDA : Usa a GPU para otimizar o seu código. Rodar mais rápido.

## Comandos do Environment

-> "activate ." dentro do env.
-> 

$$
\sum_{x = 1}^n Te amo Sabrina
$$