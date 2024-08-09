Todo arquivo ".c" passa por um processo que não é exposto para a maior parte dos usuários. Isso porque, em certo nível, C pode ser considerada uma linguagem de alto nível. 

No geral, passamos por três grandes partes na compilação de um código C: **Compilação**, **Montagem**, **Linkagem**. 

### Compilação.
Na parte da compilação o que fazemos é simplesmente converter todos os arquivos ".c" para arquivos de linguagem de montagem ".s".

### Montagem.
Todos os arquivos com extensão ".s" passam por um processo de objetificação, vamos por assim dizer. Nele transformamos todos os arquivos em códigos de máquina que se tornam altamente complexos para seres humanos entenderem. Aqui ainda não conseguimos rodar o binário, uma vez que ainda temos vários arquivos ".o" espalhados sem nenhuma conexão.

### Linkagem
Por último, temos a parte de linkagem dos arquivos objeto e das bibliotecas. O resultado final é um executável.

![[Processo_compilacao_GNU.png]]