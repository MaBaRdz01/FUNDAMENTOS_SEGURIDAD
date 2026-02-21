## RETO
binhexa
## DESCRIPCION
How well can you perfom basic binary operations?Start searching for the flag here `nc titan.picoctf.net 58537`
## SOLUCION
1. **Binary Number 1 → Decimal

`11101000`

Posiciones:  
128 64 32 16 8 4 2 1  
1 1 1 0 1 0 0 0

Suma:  
128 + 64 + 32 + 8 = **232**

 **Binary Number 2 → Decimal

`11000100`

128 64 32 16 8 4 2 1  
1 1 0 0 0 1 0 0

Suma:  
128 + 64 + 4 = **196**

 **Multiplicación 

232 × 196 = **45472**

Ahora a binario:

45472 = **1011000110100000**

 Resultado:  
`1011000110100000`

---

2. **OR |

Regla:  
1 | 1 = 1  
1 | 0 = 1  
0 | 0 = 0

  11101000  
| 11000100  
-----------  
  11101100

Resultado:  
`11101100`



3.  **Left Shift << 1 (Número 1)

Desplazar a la izquierda = multiplicar ×2

11101000  →  111010000
 Resultado:  
`111010000`

---

4. **Right Shift >> 1 (Número 2)

Desplazar a la derecha = dividir ÷2

11000100 → 01100010

 Resultado:  
`01100010`



5. **Suma +

232 + 196 = **428**

428 en binario:

428 = **110101100**

Resultado:  
`110101100`

---

**AND &

Regla:  
1 & 1 = 1  
1 & 0 = 0  
0 & 0 = 0

  11101000  
& 11000100  
-----------  
  11000000

Resultado:  
`11000000`

---

6. Conversión final a Hexadecimal

`11000000`

Agrupo en 4 bits:

1100 0000  
  C    0
## NOTAS ADICIONALES
┌──(kali㉿kali)-[~]
└─$ nc titan.picoctf.net 56905

Welcome to the Binary Challenge!"
Your task is to perform the unique operations in the given order and find the final result in hexadecimal that yields the flag.

Binary Number 1: 11101000
Binary Number 2: 11000100


Question 1/6:
Operation 1: '*'
Perform the operation on Binary Number 1&2.
Enter the binary result: 1011000110100000
Correct!

Question 2/6:
Operation 2: '|'
Perform the operation on Binary Number 1&2.
Enter the binary result: 11101100
Correct!

Question 3/6:
Operation 3: '<<'
Perform a left shift of Binary Number 1 by 1 bits.
Enter the binary result: 111010000
Correct!

Question 4/6:
Operation 4: '>>'
Perform a right shift of Binary Number 2 by 1 bits .
Enter the binary result: 01100010
Correct!

Question 5/6:
Operation 5: '+'
Perform the operation on Binary Number 1&2.
Enter the binary result: 110101100
Correct!

Question 6/6:
Operation 6: '&'
Perform the operation on Binary Number 1&2.
Enter the binary result: 11000000
Correct!

Enter the results of the last operation in hexadecimal: C0

Correct answer!
The flag is: **picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_6ab1ad84}**
## REFERENCIAS