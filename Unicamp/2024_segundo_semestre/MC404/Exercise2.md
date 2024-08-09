Geralmente uma aplicação desenvolvida em C faz todos os passos que um programados não precisa dentro da linguagem de montagem. Desse modo, o próprio compilador inicia a rotina "start" e ao desempilhar a função main realiza a chamada do "function exit".

A nosso compilador de linguagem de montagem não faz isso de maneira automática. Por conta disso, precisamos definir a execução de uma rotina de inicialização padrão do C.

```C
void exit(int code){
	__asm__ __volatile__(
		"mv a"	
	);
}
```