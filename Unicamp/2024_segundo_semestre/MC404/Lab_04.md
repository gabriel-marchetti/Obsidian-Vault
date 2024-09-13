Sobre a questão do chmod no material de referência do professor. Quanto usamos
```bash
chmod 761 file.txt
```

Primeiramente 761 é em Base Octal. Portanto, cada um desses dígitos é uma máscara para a permissão de cada entidade (owner, group, other). 
Veja que isso se torna especialmente interessante quando você começa a trabalhar com servidores, pensemos no seguinte caminho dentro de um servidor.

```
/home/gabriel/projeto/src.c
```

Veja que se dermos a permissão 701 em gabriel, então conseguimos realizar ordens de execução dentro desse diretório. Se tivermos acesso ao projeto, então podemos dar cd dentro do projeto.