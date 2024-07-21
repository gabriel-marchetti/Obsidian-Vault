O powershell funciona através de cmdlets que são encapsulamento de tarefas que o script deve fazer. Tarefas como gerenciar usuários e automatizar fluxos de trabalho são feitas através do powershell.

O powershell utiliza das pipelines onde a saída de uma função será utilizada com entrada para uma próxima função.

O powershell também utiliza de Aliases que são nomes alternativos para comandos.

cmdlets são nomeados a partir de um padrão verbo-substantivo.

Temos como buscar cmdlets através do próprio terminal. Por exemplo, temos o comando Get-Command que irá listar todos os comandos disponíveis dentro da instalação do powershell.

Contudo, listaremos milhares de comandos, desse modo temos que filtrar os comandos. Uma maneira de fazer isso é através dos argumentos -Noun e -Verb que se referem justamente ao padrão verbo-substantivo. 