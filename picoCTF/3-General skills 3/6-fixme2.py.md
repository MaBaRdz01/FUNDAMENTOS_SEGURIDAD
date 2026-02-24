## RETO
fixme2.py
## DESCRIPCION
Fix the syntax error in the Python script to print the flag. [Download Python script](https://artifacts.picoctf.net/c/6/fixme2.py)
## SOLUCION
┌──(kali㉿kali)-[~/Downloads]
└─$ python3 fixme2.py
  File "/home/kali/Downloads/fixme2.py", line 22
    if flag = "":
       ^^^^^^^^^
SyntaxError: invalid syntax. Maybe you meant '==' or ':=' instead of '='?

┌──(kali㉿kali)-[~/Downloads]
└─$ ==nano fixme2.py==   
(abrí el archivo para corregir)

┌──(kali㉿kali)-[~/Downloads]
└─$ python3 fixme2.py
That is correct! Here's your flag: **picoCTF{3qu4l1ty_n0t_4551gnm3nt_f6a5aefc}**
## NOTAS ADICIONALES
***Nano*** es un editor 

Un solo signo `=` se usa para **asignar** un valor. Para **comparar** si algo es igual a otra cosa, debes usar el doble signo `==`.

## REFERENCIAS
https://askubuntu.com/questions/1492296/how-can-i-open-the-init-py-file-to-edit-it