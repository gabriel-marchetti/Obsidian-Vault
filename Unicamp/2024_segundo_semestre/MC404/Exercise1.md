Nesse exercício devemos manejar o processo de compilação de arquivos ".c". Por conta disso, devemos fazer o processo de criação do arquivo em linguagem de montagem, posteriormente a criação do binário e por fim a ligação entre os arquivos. Esse exemplo é simples e vamos tratar de dois arquivos "file1.c" e "file2.c".

```C
extern void write(int __fd, const void *__buf, int __n);

int main(void){
	const char str[] = "Hello world!\n";
	write(1, str, 13);
	return 0;
}
```
Filename: file1.c

Aqui definimos uma função muito simples que espera receber a definição de uma função 'write' que aparenta escrever coisas no console.

```C
extern int main(void);

void exit(int code){
	__asm__ __volatile__(
	"mv a0, %0     #return code\n"
	"li a7, 93     #syscall exit (64)\n"
	"ecall"	
	:
	:"r"(code)
	:"a0", "a7"
	);
}

void write(int __fd, const void *__buf, int __n){
	__asm__ __volatile__(
	"mv a0, %0    #file descriptor\n"
	"mv a1, %1    #buffer\n"
	"mv a2, %2    #size\n"
	"li a7, 64    #syscall write (64)\n"
	:
	:"r"(__fd), "r"(__buf), "r"(__n)
	:"a0", "a1", "a2", "a7"
	);
}

void _start(){
	int ret_code = main();
	exit(ret_code);
}
```
Filename: file2.c

Aqui já tem várias funções que eu não conheço. Então seria uma ótima prática retornar aqui depois de um andamento do curso para ver se consigo entender melhor o código.