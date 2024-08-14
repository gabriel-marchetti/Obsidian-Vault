Nesse Lab foi requisitado que usássemos a ferramenta de depurar código dentro do simulador de RISC-V. Assim, foram mostrados alguns comandos que seriam úteis para depurarmos nosso programa.

Comandos Utilizados:
	step <number>
	step 
	symbols
	peek m <address>
	peek r <register_name>
	until <memory_address>

1) Para a primeira questão bastava utilizar o comando "symbols" para verificar o endereço de memória que o "end" estava localizado. Assim bastava utilizar o comando "until" com o endereço descoberto.
2) Nesse problema bastava extrair o endereço de "loop" através de "symbols". A partir disso, podíamos fazer "until" com o endereço de "loop", assim demos "step" e realizamos novamente o comando "until". Fazendo isso cinco vezes basta verificarmos as informações.
3) Basta executar o comando "step" com o número de comandos que desejamos avançar.
4) Análogo a (2)
5) Análogo a (3)
6) Basta ficar fazendo a combinação de comandos até que a condição seja verdade.
7) Por último precisamos pular até a parte desejada do código e depois precisamos extrair o endereço de "result" através de symbols. Assim usando o comando peek m <memory_address> descobrimos o valor que está dentro de "result".
