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
	)
}
```
