Mesmo que algumas pessoas digam que C é uma linguagem de alto nível, ela não é encarada como tal. Isso ocorre, visto que comparada aos métodos como perfuração de cartão ou até mesmo a programação através de uma linguagem de montagem (Assembly) ela utiliza de abstrações muito úteis. Contudo, no contexto dos dias atuais linguagens como Python ou até mesmo o Java utilizam de ferramentas muito mais abstratas para funcionar, como por exemplo o Garbage Collector.

O começo de toda a programação é através do código:

```C
#include <stdio.h>

int main(void){
	printf("Hello World!\n");

	return 0;
}
```

Eu já estou cansado de ver o que esse código faz, mas algumas palavras interessantes foram citadas e acho que elas irão agregar no meu conhecimento. Especificamente na parte "include <stdio.h>", afinal o que essa linha faz e por que ela é tão importante para o trecho de código? Visto que se retirarmos ela nada acontece.

Primeiro devemos entender que há dois estágios dentro do processo de compilação: o pré-processamento e a compilação. Tudo que começa com "#" é operado pelo pré-processamento, chamamos algumas rotinas específicas de diretivas do pré-processamento, alguns exemplos comuns disso são "define" e "include".

![[Diagrama_execucao]]

Note um detalhe importante de qual o nome do arquivo que adicionamos na diretiva "include". Veja que estamos com "stdio.h" o '.h' é o que indicamos como o "header" do arquivo. Dentro desse arquivo temos os cabeçalhos das funções que são definidas pelo arquivo "stdio.c" que contém diversas funções para entrada e saída de arquivos.
OBS: Veja que hoje em dia é muito dificil que linguagens modernas tenham uma definição tão explícita de um cabeçalho. Mas lembre que C é uma linguagem antiga e seu desenvolvimento muitas vezes se deu sem o auxílio de uma IDE.



