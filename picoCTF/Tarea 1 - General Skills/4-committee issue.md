## RETO
committee issue
## DESCRIPCION
I accidentally wrote the flag down. Good thing I deleted it! You download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/75/challenge.zip)
## SOLUCION
┌──(kali㉿kali)-[~/Downloads]
└─$ ==unzip challenge.zip==
Archive:  challenge.zip
   creating: drop-in/
   creating: drop-in/.git/
   creating: drop-in/.git/branches/
  inflating: drop-in/.git/description  
   creating: drop-in/.git/hooks/
  inflating: drop-in/.git/hooks/applypatch-msg.sample  
  inflating: drop-in/.git/hooks/commit-msg.sample  
  inflating: drop-in/.git/hooks/fsmonitor-watchman.sample  
  inflating: drop-in/.git/hooks/post-update.sample  
  inflating: drop-in/.git/hooks/pre-applypatch.sample  
  inflating: drop-in/.git/hooks/pre-commit.sample  
  inflating: drop-in/.git/hooks/pre-merge-commit.sample  
  inflating: drop-in/.git/hooks/pre-push.sample  
  inflating: drop-in/.git/hooks/pre-rebase.sample  
  inflating: drop-in/.git/hooks/pre-receive.sample  
  inflating: drop-in/.git/hooks/prepare-commit-msg.sample  
  inflating: drop-in/.git/hooks/update.sample  
   creating: drop-in/.git/info/
  inflating: drop-in/.git/info/exclude  
   creating: drop-in/.git/refs/
   creating: drop-in/.git/refs/heads/
 extracting: drop-in/.git/refs/heads/master  
   creating: drop-in/.git/refs/tags/
 extracting: drop-in/.git/HEAD       
  inflating: drop-in/.git/config     
   creating: drop-in/.git/objects/
   creating: drop-in/.git/objects/pack/
   creating: drop-in/.git/objects/info/
   creating: drop-in/.git/objects/ed/
 extracting: drop-in/.git/objects/ed/5937346e2f3d04b2481120ac1eb6fc92e9f975  
   creating: drop-in/.git/objects/eb/
 extracting: drop-in/.git/objects/eb/fc561e7c4130f03f3a668ce0609195788f1592  
   creating: drop-in/.git/objects/66/
 extracting: drop-in/.git/objects/66/03cb4ff0c4ea293798c03a32e0d78d5ab12ca2  
   creating: drop-in/.git/objects/d5/
 extracting: drop-in/.git/objects/d5/52d1ecd2d83fa2e65b6724d1ff73b45a7d59b7  
   creating: drop-in/.git/objects/0c/
 extracting: drop-in/.git/objects/0c/1ab266b7a3a1cd099bb509f82b7a2d03aecd03  
   creating: drop-in/.git/objects/38/
 extracting: drop-in/.git/objects/38/99edb7f3110d613c72ad40083fd8feeef703d0  
  inflating: drop-in/.git/index      
 extracting: drop-in/.git/COMMIT_EDITMSG  
   creating: drop-in/.git/logs/
  inflating: drop-in/.git/logs/HEAD  
   creating: drop-in/.git/logs/refs/
   creating: drop-in/.git/logs/refs/heads/
  inflating: drop-in/.git/logs/refs/heads/master  
 extracting: drop-in/message.txt     

┌──(kali㉿kali)-[~/Downloads]
└─$ ==ls -la==
total 7216
drwxr-xr-x   6 kali kali    4096 Feb 20 23:00 .
drwx------  17 kali kali    4096 Feb 20 23:00 ..
drwxr-xr-x   3 kali kali    4096 Dec 12 14:21 Addadshashanammu
-rw-rw-r--   1 kali kali    5166 Feb 11 19:02 Addadshashanammu.zip
drwxrwxr-x 121 kali kali   36864 May  3  2020 big-zip-files
-rw-rw-r--   1 kali kali 3182988 Feb 11 22:42 big-zip-files.zip
-rw-rw-r--   1 kali kali   19196 Feb 20 22:51 challenge.zip
-rw-rw-r--   1 kali kali      27 Feb 13 00:41 codebook.txt
-rw-rw-r--   1 kali kali    1278 Feb 13 00:41 code.py
-rw-rw-r--   1 kali kali    1189 Feb 13 00:54 convertme.py
drwxr-xr-x   3 kali kali    4096 Mar  9  2024 drop-in
-rw-rw-r--   1 kali kali     349 Feb 11 22:28 enc_flag
drwxrwxr-x   5 kali kali    4096 May 13  2022 files
-rw-rw-r--   1 kali kali 3995553 Feb 11 22:53 files.zip
-rw-rw-r--   1 kali kali     835 Feb 13 01:13 fixme1.py
-rw-rw-r--   1 kali kali    1030 Feb 13 01:31 fixme2.py
-rw-rw-r--   1 kali kali      30 Feb 13 01:36 level1.flag.txt.enc
-rw-rw-r--   1 kali kali     876 Feb 13 01:36 level1.py
-rw-rw-r--   1 kali kali      31 Feb 13 01:52 level2.flag.txt.enc
-rw-rw-r--   1 kali kali     914 Feb 13 01:52 level2.py
-rw-rw-r--   1 kali kali      31 Feb 14 00:20 level3.flag.txt.enc
-rw-rw-r--   1 kali kali      16 Feb 14 00:20 level3.hash.bin
-rw-rw-r--   1 kali kali    1337 Feb 14 00:20 level3.py
-rw-rw-r--   1 kali kali     785 Feb 11 14:07 ltdis.sh
-rw-rw-r--   1 kali kali    2570 Feb 14 01:31 serpentine.py
-rw-rw-r--   1 kali kali   16776 Feb 11 14:07 static
-rw-rw-r--   1 kali kali    1699 Feb 11 18:14 static.ltdis.strings.txt
-rw-rw-r--   1 kali kali    6328 Feb 11 18:14 static.ltdis.x86_64.txt
-rwxrwxr-x   1 kali kali   19312 Feb 11 13:55 warm

┌──(kali㉿kali)-[~/Downloads]
└─$ ==ls==
Addadshashanammu      challenge.zip  **drop-in**    fixme1.py            level2.flag.txt.enc  level3.py      static.ltdis.strings.txt
Addadshashanammu.zip  codebook.txt   enc_flag   fixme2.py            level2.py            ltdis.sh       static.ltdis.x86_64.txt
big-zip-files         code.py        files      level1.flag.txt.enc  level3.flag.txt.enc  serpentine.py  warm
big-zip-files.zip     convertme.py   files.zip  level1.py            level3.hash.bin      static

┌──(kali㉿kali)-[~/Downloads]
└─$ ==cd drop-in==  

┌──(kali㉿kali)-[~/Downloads/drop-in]
└─$ ==ls -la==
total 16
drwxr-xr-x 3 kali kali 4096 Mar  9  2024 .
drwxr-xr-x 8 kali kali 4096 Feb 20 23:04 ..
**==drwxr-xr-x 8 kali kali 4096 Mar  9  2024 .git==**
-rw-r--r-- 1 kali kali   11 Mar  9  2024 message.txt

┌──(kali㉿kali)-[~/Downloads/drop-in]
└─$ ==git init==         
Reinitialized existing Git repository in /home/kali/Downloads/drop-in/.git/

┌──(kali㉿kali)-[~/Downloads/drop-in]
└─$ ==git log== 
commit 3899edb7f3110d613c72ad40083fd8feeef703d0 (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:09:58 2024 +0000

    remove sensitive info

commit 6603cb4ff0c4ea293798c03a32e0d78d5ab12ca2
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:09:58 2024 +0000

    create flag

┌──(kali㉿kali)-[~/Downloads/drop-in]
└─$ ==git checkout 6603cb4ff0c4ea293798c03a32e0d78d5ab12ca2==
Note: switching to '6603cb4ff0c4ea293798c03a32e0d78d5ab12ca2'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 6603cb4 create flag

┌──(kali㉿kali)-[~/Downloads/drop-in]
└─$ ==ls==           
message.txt

┌──(kali㉿kali)-[~/Downloads/drop-in]
└─$ ==cat message.txt== 
**picoCTF{s@n1t1z3_9539be6b}**


## NOTAS ADICIONALES
- .git  carpeta :indica que el directorio es un repositorio de Git. Esta carpeta contiene toda la historia del proyecto.
- git init : es el ==comando fundamental en Git para **crear un nuevo repositorio local vacío** en el directorio actual o inicializar uno nuevo==.
- git log : es una utilidad fundamental de Git que se utiliza para mostrar el historial registrado de confirmaciones en un repositorio.
- git checkout 6603cb4ff0c4ea293798c03a32e0d78d5ab12ca2 :Este comando le traslada al estado del repositorio cuando el `message.txt`El archivo fue creado.


## REFERENCIAS
[https://git-scm.com/book/es/v2/Inicio---Sobre-el-Control-de-Versiones-Configurando-Git-por-primera-vez](https://primer.picoctf.org/#_git_version_control)