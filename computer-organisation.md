    github.com/tangboxuan

## Number Systems

|System|Value|-x|Negation|Addition|Overflow
|:---:|:---:|:---:|:---:|:---:|:---:
|Sign & Magnitude|||Invert first bit|
|1s Complement|+ve: same as 2s<br>-ve: 2s + 1|2^n - x - 1|Invert all bits|If MSB carry out: +=1|Result opposite sign of A and B|
|2s Complement|if x[n-1]: -= 2^(n-1)<br>for i in [n-2..0]:<br>if x[i]: += 2^i|2^n - x|Invert all bits + 1|Ignore MSB carry out|MSB carry in != MSB carry out<br>Result opposite sign of A and B|
|Excess-n|x-n
|IEEE 754|(Sign) (1.Mantissa) x 2^Exponent||Invert first bit|1: Sign<br>8: Ex-127 Exp|---<br>23: Mantissa

## MIPS


|Operation| RR1| RR2| WR| WD| Opr1| Opr2| Address| Write Data|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:
|lw $a, x($b)|	$b|	$a|	$a|	Mem([$b] +x)| [$b]|	x|	[$b] + x	|[$a]|
|beq $a,$b, immd|	$a|	$b|	$b|	? |	[$a]|	[$b]|	[$a] - [$b]|	[$b]|
|sub $a, $b, $c|	$b|	$c|	$a|	[$b] – [$c]|	[$b]|	[$c]|	[$b] – [$c]|	[$c]|
|addi $a, $b, immd|	$b|	$a|	$a| [$b] + immd| [$b]| immd| [$b]	+ immd| [$a]						

<div style="page-break-after: always;"></div>

![MIPS](images/mips.jpg)

<div style="page-break-after: always;"></div>

![Control](images/control.png)
![Datapath](images/datapath.jpg)

<div style="page-break-after: always;"></div>

![Add: Chong Wen Hao](images/dp_add.png)
![BEQ: Chong Wen Hao](images/dp_beq.png)
![LW: Chong Wen Hao](images/dp_lw.png)
![SW: Chong Wen Hao](images/dp_sw.png)

<div style="page-break-after: always;"></div>

![ALUcontrol](images/ALUcontrol.png)
![ALU](images/ALU.png)

## Links

[Hexadecimal to Float](https://babbage.cs.qc.cuny.edu/IEEE-754.old/32bit.html)  
[Hexadecimal-Binary-Decimal](https://www.rapidtables.com/convert/number/binary-to-hex.html)  
[XOR](http://xor.pw/#)  
[Bitwise Calculator](https://miniwebtool.com/bitwise-calculator/)  
[Instructions to Hexadecimal](https://www.eg.bucknell.edu/~csci320/mips_web/)  
