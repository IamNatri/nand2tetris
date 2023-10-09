
# Capítulo 2 - Boolean Arithmetic and the ALU

### Realizado
* implementação do Half Adder, Full Adder, 16-bit Adder, 16-bit incrementer e ALU Unidade Lógico-Aritmética).

### Observações 

* Se você deseja usar apenas uma parte do output de um barramento de vários bits (por exemplo, a[n], a[n..m], etc.), é necessário fazer um desvio durante a saída do output do barramento de vários bits.

    * Especificar apenas uma parte dos pinos do barramento de vários bits durante a entrada resultará em erro.


    ``` VHDL
        // OK
        Mux16 (a=pin16, b=false, sel=false, out=out, out[0..7]=out0to7, out[8..15]=out8to15); 
        Or8Way (in=out0to7, out=or0to7);
        Or8Way (in=out8to15, out=or8to15);

        // ERROR
        Mux16 (a=pin16, b=false, sel=false, out=out); 
        Or8Way (in=out[0..7], out=or0to7);
        Or8Way (in=out[8..15], out=or8to15);
    ```