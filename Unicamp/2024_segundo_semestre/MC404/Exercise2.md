Geralmente uma aplicação desenvolvida em C faz todos os passos que um programados não precisa dentro da linguagem de montagem. Desse modo, o próprio compilador inicia a rotina "start" e ao desempilhar a função main realiza a chamada do "function exit".

A nosso compilador de linguagem de montagem não faz isso de maneira automática. Por conta disso, precisamos definir a execução de uma rotina de inicialização padrão do C.

```C
void exit(int code){
	__asm__ __volatile__(
		"mv a0, %0    #return code\n"	
		"li a7, 93    #syscall exit(64)\n"
		"ecall"
		:    // Output List
		:"r"(code) // Input List
		:"a0", "a7"
	);
}

void _start(){
	int ret_code = main();
	exit(ret_code);
}
```

Além disso, temos que o Sistema Operacional não consegue diretamente atuar em periféricos, portanto, utilizamos de system calls (syscalls) para lidar com isso. 

Para isso, quando abrimos algum arquivo o sistema operacional irá gerar um "file descriptor" desse arquivo e o programa irá utilizar esse "file descriptor". Temos que existem três "files descriptors" que sempre podem ser usadas pelo programador elas são: STDIN, STDOUT, STDERR e seus valores são, respectivamente 0, 1 e 2. 

```C
/*
 * read
 * Parameters:
 * __fd: file descriptor of the file to be read.
 * __buf: buffer to store the data read.
 * __n: maximum amount of bytes to be read.
 * Return:
 *     Number of bytes read.
 */

int read(int __fd, const void *__buf, int __n){
	int ret_val;
	__asm__ __volatile__(
	"mv a0, %1 # file descriptor\n"	
	"mv a1, %2 # buffer\n"
	"mv a2, %3 # size\n"
	"li a7, 63 # syscall read code (63)"  
	);
}
```