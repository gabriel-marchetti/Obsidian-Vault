ISA significa "Instruction Set Architecture". Portanto, não é incomum encontrar RV32I ISA. Cada letra seguida do "RV32" define um tipo de extensão que a arquitetura pode receber, contudo, não vale a pena entrar em detalhes por aqui! Apenas é interessante saber que iremos usar principalmente a arquitetura RV32IM ISA, que define operações básicas, de multiplicação e de divisão. 

Algumas das propriedades interessantes de serem comentadas, entretanto, são:
- 32-bit address spaces.
- contains 33 32-bit registers.
- signed integers are represented with two's complement.

Os tipos nativos da ISA do RV32I são:

|   Datatype name   | size in bytes |
| :---------------: | :-----------: |
|       byte        |       1       |
|   unsigned byte   |       1       |
|     halfword      |       2       |
| unsigned halfword |       2       |
|       word        |       4       |
|   unsigned word   |       4       |

Veja que aqui é importante notas que a arquitetura utiliza do fato dos computadores terem "como padrão" byte-addressable memory.

Além disso, é interessante saber que qualquer linguagem com abstração acima da do RV32I, mas que converta seu código para essa arquitetura, terá que converter seus tipos para algum dos tipos mostrados acima. Por exemplo, um ponteiro dentro do C nada mais é que um endereço de memória, portanto, o compilador irá transformá-la em um "unsigned word" para a arquitetura de 32 bits.

## RV32I Registers
O RV32I possui trinta e três registradores de 32-bits com propósito geral. Seus nomes são geralmente associados a x0-x31 e o pc.
pc -> program counter: armazena o endereço de memória da próxima instrução
x0 -> armazena zero, mesmo que você tente sobrescrever
x1-x31 -> registradores de propósito geral, contudo, temos uma convenção.

## Load/Store Architecture.
A arquitetura RV32I possui o padrão de operação de carregar/salvar dados na memória. Isto é, antes de realizar uma operação de um inteiro já conhecido, primeiro temos que olhar para seu conteúdo da memória e depois de realizar as operações temos que salvá-lo na memória.

## Logic, shift and arithmetic 
Todas essa operações possuem um padrão do Mnemônico seguido de três operandos. O primeiro operando é o alvo que irá receber o resultado da operação, enquanto os outros dois são os argumentos da operação.

```
MNM rd, rs1, rs2
MNM rd, rs1, imm
```

rd: target register
rs1: first operand register
rs2: second operand register
imm: immediate.

```rv32
and a0, a2, a6 # a0 := a2 & a6
slli a1, a3, 2 # a1 := a3 << 2
sub a4, a5, a6 # a4 := a5 - a6
```

## Dealing with large immediate
Notemos que todas as operações do RV32I são codificados em algum número de 32-bits. Portanto, fica claro que temos uma aparente limitação se estamos trabalhando com imediatos grandes, uma vez que teremos menos do que 