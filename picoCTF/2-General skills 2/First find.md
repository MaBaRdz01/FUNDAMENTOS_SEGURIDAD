## RETO
First Find
## DESCRIPCION
Unzip this archive and find the file named 'uber-secret.txt'

- [Download zip file](https://artifacts.picoctf.net/c/501/files.zip)
## SOLUCION

┌──(kali㉿kali)-[~/Downloads]
└─$ ls
Addadshashanammu      big-zip-files.zip  files.zip  static.ltdis.strings.txt
Addadshashanammu.zip  enc_flag           ltdis.sh   static.ltdis.x86_64.txt
big-zip-files         files              static     warm

┌──(kali㉿kali)-[~/Downloads]
└─$ ==strings files.zip | grep pico==                   
**picoCTF{f1nd_15_f457_ab443fd1}**

## NOTAS ADICIONALES
strings    -> extraemos el texto de la carpeta file.zip

grep       -> buscamos pico

## REFERENCIAS
https://medium.com/@tong33/first-find-picoctf-d82dcc196465