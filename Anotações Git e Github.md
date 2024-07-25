```C
#include <stdio.h>
#include <stdlib.h>

int main()
{
	printf("Hello, World!\n");
	return 0;
}
```

Primeiro precisamos saber como inicializar o <mark style="background: #FF5582A6;">git</mark> dentro de um repositório, desse modo, podemos criar um arquivo através do <mark style="background: #ADCCFFA6;">bash</mark> do linux:
```
>> mkdir <nome-do-repositorio>
```

Após isso teremos o nosso repositório com nome <nome-do-repositorio> podemos entrar nele usando o comando padrão cd <nome-do-repositorio>.

Após estar dentro do nosso ambiente (ou repositório), podemos simplesmente inicializar o <mark style="background: #FF5582A6;">git</mark> através do comando.

```
>> git init
```

Parecerá que não fizemos nada até o momento, contudo, podemos usar o comando

```
>> ls -a
```

Veremos que aparecerá uma pasta escondida <.git> nesse caso quer dizer que tivemos sucesso em realizar nossa inicialização do <mark style="background: #FF5582A6;">git</mark>!

## Git Status 

Agora veremos como podemos usar o comando "git status". Dentro do repositório git podemos simplesmente escrever a linha de código:

```
>> git status
```

Nesse caso aparecerá se há alguma mudança dentro do seu arquivo, nesse caso, se não houver podemos prosseguir fazendo as mudanças. Caso haja alguma mudança, precisamos nos atentar a duas etapas:

### Staging 

Suponhamos que estamos trabalhando num arquivo que possui diversos arquivos, podem ser centenas ou até milhares de arquivos. Então podemos fazer pequenas mudanças, isto é, suponhamos que nosso trabalho seja que o arquivo <mark style="background: #FFB8EBA6;">file1.c</mark> faça a operação X. Entretanto, nosso diretório possui uma infinidade de arquivos que fazem outras tarefas diversas. Desse modo, queremos apenas alterar momentaneamente o <mark style="background: #FFB8EBA6;">file.c</mark> para fazer a tarefa X. 

Para adicionar um arquivo à região de staging podemos simplesmente escrever:

```
>> git add file.c
```
OBS: um shortcut para adicionarmos todos os arquivos que aparecem no git status é através do comando:
```
>> git add .
```


Se escrevermos novamente o comando:

```
>> git status
```

Veremos que algumas mudanças já terão sido feitas, de modo que agora podemos realizar um commit! 

### Commit

Após adicionarmos nossos arquivos no stage tudo que nos resta fazer é realizar o commit. Desse modo, podemos escrever a seguinte linha de comando:

```
>> git commit -m "Commit message."
```

### Git log

O comando:
```
>> git log
```
Passa o histórico de commit que foram realizados.

### Git checkout

A utilidade do git log não é somente termos um registro das mudanças dos nossos arquivos! É também para conseguirmos voltar em algum ponto antes de alguma mudança, por exemplo:

```
>> git checkout <git-hash>
```

## Branches:

Um Branch é uma maneira de organizarmos nosso código, de modo que se quisermos testar alguma nova ideia nos basta criarmos uma Branch e avaliar se o que fizemos foi bom.

### Creating a new Branch:

```
>> git branch <new-branch-name>
```





