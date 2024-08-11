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
	"li a7, 63 # syscall read code (63)\n"
	"ecall     # invoke syscall\n" 
	"mv %0, a0 # move return value ret_val\n"
	: "=r"(ret_val) // Output List
	: "r"(__fd), "r"(__buf), "r"(__n) // Input List
	: "a0", "a1", "a2", "a7"
	);
	return ret_val;
}
```

Aqui podemos ver a utilidade do "file descriptor", uma vez que queremos ler as entradas do usuário então queremos utilizar o STDIN (0). Veja que necessitamos de alocar um buffer para essa função que possui um máximo de bytes. 

Para utilizar essa função podemos fazer:
```C
/* Allocate the buffer that will be used. */
char input_buffer[10];
/* we expect some definition of read */
extern int read(int, const void*, int);

int main(){
	int n = read(0, (void*) input_buffer, 10);

	return 0;
}

```

Do mesmo modo que fizemos com a função read, agora podemos fazer para uma função que escreva no terminal.

```C
/* write
 * Parameters:
 * __fd: file descriptor where we will write code.
 * __buf: buffer with the data we want to write.
 * __n: amount of bytes to be written.
 * Return:
 *  Number of bytes effectively written.
 */

void write(int __fd, const void *__buf, int __n){
	__asm__ __volatile__(
	"mv a0, %0 # file descriptor\n"	
	"mv a1, %1 # buffer\n"
	"mv a2, %2 # size\n"
	"li a7, 64 # syscall write (64)\n"
	"ecall"
	: // Output List
	:"r"(__fd), "r"(__buf), "r"(__n) //Input List
	:"a0", "a1", "a2", "a7"
	);
}
```

Um jeito de utilizar essa função é:

```C
/* Allocates a global string with 5 bytes.
 *   Note: the break line character, \n is encoded
 *       with a single byte 
 */
extern void write(int, const void*, int);
char my_string[] = "1969\n";

int main()
{
  /* Prints the first 5 characters from the string on
   * the standard output, in other words, 1, 9, 6, 9 and break line. */
  write(1, my_string, 5);

  return 0;
}

```

OBS: Para não termos que alocar espaço extra dentro de "my_string" podemos criar um buffer auxiliar para armazenar apenas a quebra de linha.