## RETO
time machine
## DESCRIPCION
What was I last working on? I remember writing a note to help me remember... You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/66/challenge.zip)

## SOLUCION
1. Se descomprime
2. 
┌──(kali㉿kali)-[~/Downloads]
└─$ ==cd drop-in==
 
┌──(kali㉿kali)-[~/Downloads/drop-in]
└─$ ==ls==
message.txt

En el siguiente comando, muestran pista:
┌──(kali㉿kali)-[~/Downloads/drop-in]
└─$ ==cat message.txt==
**This is what I was working on, but I'd need to look at my commit history to know why...**                                                                                                                                                                      
┌──(kali㉿kali)-[~/Downloads/drop-in]
└─$ ==ls -la==
total 16
drwxr-xr-x 3 kali kali 4096 Mar  9  2024 .
drwxr-xr-x 6 kali kali 4096 Feb 20 23:28 ..
**drwxr-xr-x 8 kali kali 4096 Mar  9  2024 .git**
-rw-r--r-- 1 kali kali   87 Mar  9  2024 message.txt

┌──(kali㉿kali)-[~/Downloads/drop-in]
└─$ ==git log==                                              
commit 3339c144a0c78dc2fbd3403d2fb37d3830be5d94 (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:10:22 2024 +0000

**picoCTF{t1m3m@ch1n3_d3161c0f}**

## NOTAS ADICIONALES
Basándome en la pista que se dio después de mostrar el contenido del archivo usando el comando `cat`, sospeché que podía haber un repositorio Git oculto. Pensé que algo pudo haber sido modificado o eliminado y que la flag estaría en commits anteriores. Para verificarlo, ejecuté `ls -la`, donde observé la presencia del directorio `.git`. Posteriormente, utilicé `git log` para revisar el historial de commits, y allí apareció la flag.
## REFERENCIAS
https://primer.picoctf.org/#_git_version_control