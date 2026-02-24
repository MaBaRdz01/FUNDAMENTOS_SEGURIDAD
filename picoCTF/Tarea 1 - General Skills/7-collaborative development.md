## RETO
collaborative development
## DESCRIPCION
My team has been working very hard on new features for our flag printing program! I wonder how they'll work together?You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/179/challenge.zip)
## SOLUCION
──(kali㉿kali)-[~/Downloads]
└─$ cat drop-in/flag.py
print("Printing the flag...")

┌──(kali㉿kali)-[~/Downloads]
└─$ ls -la            
total 40
drwxr-xr-x  3 kali kali  4096 Feb 21 00:15 .
drwx------ 17 kali kali  4096 Feb 21 00:15 ..
-rw-rw-r--  1 kali kali 24648 Feb 21 00:14 challenge.zip
drwxr-xr-x  3 kali kali  4096 Mar 11  2024 drop-in

──(kali㉿kali)-[~/Downloads]
└─$ cd drop-in         
 
┌──(kali㉿kali)-[~/Downloads/drop-in]
└─$ ls -la
total 16
drwxr-xr-x 3 kali kali 4096 Mar 11  2024 .
drwxr-xr-x 3 kali kali 4096 Feb 21 00:15 ..
-rw-r--r-- 1 kali kali   30 Mar 11  2024 flag.py
drwxr-xr-x 8 kali kali 4096 Mar 11  2024 .git

┌──(kali㉿kali)-[~/Downloads/drop-in]
└─$ git log
commit 5e4b2dae1868abb644627483c78a683286dfe67c (HEAD -> main)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:57 2024 +0000

    init flag printer
 
┌──(kali㉿kali)-[~/Downloads/drop-in]
└─$ git reflog            
5e4b2da (HEAD -> main) HEAD@{0}: checkout: moving from feature/part-3 to main
12c2ae8 (feature/part-3) HEAD@{1}: commit: add part 3
5e4b2da (HEAD -> main) HEAD@{2}: checkout: moving from main to feature/part-3
5e4b2da (HEAD -> main) HEAD@{3}: checkout: moving from feature/part-2 to main
74989a4 (feature/part-2) HEAD@{4}: commit: add part 2
5e4b2da (HEAD -> main) HEAD@{5}: checkout: moving from main to feature/part-2
5e4b2da (HEAD -> main) HEAD@{6}: checkout: moving from feature/part-1 to main
300cff1 (feature/part-1) HEAD@{7}: commit: add part 1
5e4b2da (HEAD -> main) HEAD@{8}: checkout: moving from main to feature/part-1
5e4b2da (HEAD -> main) HEAD@{9}: commit (initial): init flag printer

┌──(kali㉿kali)-[~/Downloads/drop-in]
└─$ git branch -a
  feature/part-1
  feature/part-2
  feature/part-3
* main                                       
┌──(kali㉿kali)-[~/Downloads/drop-in]
└─$ git checkout feature/part-1            
Switched to branch 'feature/part-1'

┌──(kali㉿kali)-[~/Downloads/drop-in]
└─$ ls -la
total 16
drwxr-xr-x 3 kali kali 4096 Feb 21 00:19 .
drwxr-xr-x 3 kali kali 4096 Feb 21 00:15 ..
-rw-rw-r-- 1 kali kali   64 Feb 21 00:19 flag.py
drwxr-xr-x 8 kali kali 4096 Feb 21 00:19 .git

┌──(kali㉿kali)-[~/Downloads/drop-in]
└─$ cat flag.py        
print("Printing the flag...")
print("**picoCTF{t3@mw0rk_**", end='') 

┌──(kali㉿kali)-[~/Downloads/drop-in]
└─$ git checkout feature/part-2
Switched to branch 'feature/part-2'

┌──(kali㉿kali)-[~/Downloads/drop-in]
└─$ ls -la
total 16
drwxr-xr-x 3 kali kali 4096 Feb 21 00:20 .
drwxr-xr-x 3 kali kali 4096 Feb 21 00:15 ..
-rw-rw-r-- 1 kali kali   64 Feb 21 00:20 flag.py
drwxr-xr-x 8 kali kali 4096 Feb 21 00:20 .git

┌──(kali㉿kali)-[~/Downloads/drop-in]
└─$ cat flag.py 
print("Printing the flag...")

print("**m@k3s_th3_dr3@m_**", end='')  

──(kali㉿kali)-[~/Downloads/drop-in]
└─$ git checkout feature/part-3
Already on 'feature/part-3'

┌──(kali㉿kali)-[~/Downloads/drop-in]
└─$ ls -la                     
total 16
drwxr-xr-x 3 kali kali 4096 Feb 21 00:21 .
drwxr-xr-x 3 kali kali 4096 Feb 21 00:15 ..
-rw-rw-r-- 1 kali kali   55 Feb 21 00:21 flag.py
drwxr-xr-x 8 kali kali 4096 Feb 21 00:21 .git

┌──(kali㉿kali)-[~/Downloads/drop-in]
└─$ cat flag.py                
print("Printing the flag...")

print("**w0rk_798f9981}**")


## NOTAS ADICIONALES
`git branch -a`muestra las sucursales locales


## REFERENCIAS
https://primer.picoctf.org/#_git_version_control