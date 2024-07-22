Git vs Github
	Criar várias instâncias de um trabalho, de modo que cada versão seja coerente com seu próprio contexto sem gerar ambiguidade ou confusão.

Em outras palavras, vamos supor que tenhamos a seguintes estrutura de organização: Temos uma pasta onde salvamos as versões do nosso projeto. Sabemos, por experiência, que podemos gerar um ambiente como:

![[Exemplo_Git|500]]

Veja que um método mais adequado seria algo síncrono, isto é, baseamos o nosso projeto na sua versão atual dada uma requisição de salvamento. Desse modo temos:

![[Imagem_git|500]]

Veja que se pudermos ciclar entre cada versão de modo que resgatamos as modificações anteriores, então temos um fluxo de trabalho extremamente eficiente. Esse é o papel do Git, gerenciar as versões do seu trabalho.

Veja que aqui transcendemos o nível de trabalho em equipe, uma vez que cada integrante pode gerar na sua máquina alterações no projeto sem alterar o todo e, além disso, gerar requisições de agregação das alterações. Veja que essas alterações podem ser correção de bugs, por exemplo. Assim como, criar ambientes de teste fica mais fácil.

Desse modo, criamos um novo aspecto de comunidade de modo que temos várias ferramentas para compartilhar nosso código como o GitHub, o GitBucket e o GitLab.