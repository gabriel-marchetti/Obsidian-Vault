Todo arquivo ".c" passa por um processo que não é exposto para a maior parte dos usuários. Isso porque, em certo nível, C pode ser considerada uma linguagem de alto nível. 

No geral, passamos por três grandes partes na compilação de um código C: **Compilação**, **Montagem**, **Linkagem**. 

### Compilação.
Na parte da compilação o que fazemos é simplesmente converter todos os arquivos ".c" para arquivos de linguagem de montagem ".s".

### Montagem.
Todos os arquivos com extensão ".s" passam por um processo de objetificação, vamos por assim dizer. Nele transformamos todos os arquivos em códigos de máquina que se tornam altamente complexos para seres humanos entenderem. Aqui ainda não conseguimos rodar o binário, uma vez que ainda temos vários arquivos ".o" espalhados sem nenhuma conexão.

### Linkagem
Por último, temos a parte de linkagem dos arquivos objeto e das bibliotecas. O resultado final é um executável.

![[Processo_compilacao_GNU.png]]

### Desenvolvimento
Cada um desses processos admite um comando dentro do terminal
vamos supor que estejamos trabalhando no arquivo "prog.c"

```shell
clang-15 --target=riscv32 -march=rv32g -mabi=ilp32d -mno-relax prog.c -S -o prog.s
```

Aqui geramos o arquivo em linguagem de montagem.

```shell
clang-15 --target=riscv32 -march=rv32g -mabi=ilp32d -mno-relax prog.s -c -o prog.o
```

Aqui geramos o arquivo binário sem conexão entre os arquivos.

```shell
ld.lld prog.o -o prog.x
```

Aqui geramos finalmente o arquivo executável. Veja que se tivermos diversos arquivos ".o" então precisaremos linkar todos eles aqui no final.

Veja que esse processo é muito chato. Por conta disso podemos utilizar o Makefile para automatizar boa parte do processo.

Manual Makefile: https://www.gnu.org/software/make/manual/make.html#Simple-Makefile

Página tutorial Makefile: https://pt.wikibooks.org/wiki/Programar_em_C/Makefiles