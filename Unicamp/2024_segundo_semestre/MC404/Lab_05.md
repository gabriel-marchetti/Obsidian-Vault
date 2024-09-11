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

Além disso, é interessante saber que qualquer linguagem com abstração acima da do RV32I, mas que converta seu código para essa arquitetura, terá que converter seus tipos para algum dos tipos mostrados acima. Por exemplo, um ponteiro dentro do C nada mais é que um endereço