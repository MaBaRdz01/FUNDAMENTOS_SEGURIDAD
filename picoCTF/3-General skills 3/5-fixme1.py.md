## RETO
fixme1.py
## DESCRIPCION
Fix the syntax error in this Python script to print the flag. [Download Python script](https://artifacts.picoctf.net/c/25/fixme1.py)
## SOLUCION
──(kali㉿kali)-[~/Downloads]
└─$ python3 fixme1.py  
  File "/home/kali/Downloads/fixme1.py", line 20
    print('That is correct! Here\'s your flag: ' + flag)
IndentationError: unexpected indent

ME FUI AL DOCUMENTO Y ARREGLE EL ESPACIO(SANGRIA) QUE VENIA EN LA LINEA 20. EL RESULTADO FUE:

┌──(kali㉿kali)-[~/Downloads]
└─$ python3 fixme1.py                
That is correct! Here's your flag: ==picoCTF{1nd3nt1ty_cr1515_6a476c8f}==


## NOTAS ADICIONALES
Python es sensible a los espacios mal colocados a tal grado de que te marca error.

## REFERENCIAS