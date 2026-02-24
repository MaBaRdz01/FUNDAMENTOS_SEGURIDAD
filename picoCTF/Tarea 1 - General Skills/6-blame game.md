## RETO
## DESCRIPCION
Someone's commits seems to be preventing the program from working. Who is it? You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/72/challenge.zip)
## SOLUCION
┌──(kali㉿kali)-[~/Downloads]
└─$ ==cd drop-in==     

┌──(kali㉿kali)-[~/Downloads/drop-in]
└─$ ==ls -la==
total 16
drwxr-xr-x 3 kali kali 4096 Mar  9  2024 .
drwxr-xr-x 3 kali kali 4096 Feb 21 00:06 ..
**drwxr-xr-x 8 kali kali 4096 Mar  9  2024 .git**
-rw-r--r-- 1 kali kali   22 Mar  9  2024 message.py

┌──(kali㉿kali)-[~/Downloads/drop-in]
└─$ ==git log message.py==
commit 9ae3e1bc67ad0143c611c5f65399b79850d20983
Author: **picoCTF{@sk_th3_1nt3rn_b64c4705}** <ops@picoctf.com>
Date:   Sat Mar 9 21:09:01 2024 +0000

    optimize file size of prod code

commit f3cec26cf7f80f91b5c3d1972f14dd4e9f97ec83
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:09:01 2024 +0000

    create top secret project


## NOTAS ADICIONALES
Al revisar el historial del archivo con `git log message.py`, observé que uno de los commits tenía un campo Author anómalo. En lugar del nombre estándar, contenía directamente la flag. Esto indica que la flag fue escondida en la metadata del commit y no en el contenido del archivo.

## REFERENCIAS
https://medium.com/@technolifts/picoctf-blame-game-writeup-4849f20116b9