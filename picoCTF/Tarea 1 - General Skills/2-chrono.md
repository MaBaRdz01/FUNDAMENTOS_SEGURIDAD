## RETO
chrono
## DESCRIPCION
How to automate tasks to run at intervals on linux servers?

Additional details will be available after launching your challenge instance.
## SOLUCION
1. Me conecte al un servidor picoCTF:
2. Llegue al root del sistema
picoplayer@challenge:~$ cd .. 
picoplayer@challenge:/home$ cd ..
3. enlistamos
picoplayer@challenge:/$ ls
bin   challenge  etc   lib    lib64   media  opt   root  sbin  sys  usr
boot  dev        home  lib32  libx32  mnt    proc  run   srv   tmp  var
4. intentamos entrar a challenge:
picoplayer@challenge:/$ cd challenge/
-bash: cd: challenge/: Permission denied
5. Enlistamos archivos de tal forma que muestre que permisos tiene , el dueño, tamaño y fecha :
picoplayer@challenge:/$ ls -l / 
total 0
lrwxrwxrwx 1 root root 7 Mar 8 2023 bin -> usr/bin 
drwxr-xr-x 2 root root 6 Apr 15 2020 boot
**d--------- 1 root root 27 Aug 4 2023 challenge** 
drwxr-xr-x 5 root root 340 Feb 20 20:39 dev 
drwxr-xr-x 1 root root 66 Feb 20 20:39 etc 
drwxr-xr-x 1 root root 24 Aug 4 2023 home 
lrwxrwxrwx 1 root root 7 Mar 8 2023 lib -> usr/lib 
lrwxrwxrwx 1 root root 9 Mar 8 2023 lib32 -> usr/lib32 
lrwxrwxrwx 1 root root 9 Mar 8 2023 lib64 -> usr/lib64 
lrwxrwxrwx 1 root root 10 Mar 8 2023 libx32 -> usr/libx32 
drwxr-xr-x 2 root root 6 Mar 8 2023 media 
drwxr-xr-x 2 root root 6 Mar 8 2023 mnt 
drwxr-xr-x 2 root root 6 Mar 8 2023 opt 
dr-xr-xr-x 196 nobody nogroup 0 Feb 20 20:39 proc 
drwx------ 2 root root 37 Mar 8 2023 root 
drwxr-xr-x 1 root root 54 Feb 20 20:40 run 
lrwxrwxrwx 1 root root 8 Mar 8 2023 sbin -> usr/sbin 
drwxr-xr-x 2 root root 6 Mar 8 2023 srv 
dr-xr-xr-x 13 nobody nogroup 0 Feb 20 20:39 sys 
drwxrwxrwt 1 root root 6 Aug 4 2023 tmp 
drwxr-xr-x 1 root root 18 Mar 8 2023 usr 
drwxr-xr-x 1 root root 17 Mar 8 2023 var 
6. Revisamos cron:
picoplayer@challenge:/$ cat /etc/crontab 
imprime :# **picoCTF{Sch3DUL7NG_T45K3_L1NUX_7754e199}**

## NOTAS ADICIONALES
- El nombre del reto proporciona una pista clave (_Chrono → cron_).

- La carpeta `/challenge` estaba protegida intencionalmente.

- La bandera estaba visible en un comentario dentro de `/etc/crontab`.

==**ls -l /**     -> revisamos los permisos del directorio raiz==

## REFERENCIAS
Manual de Linux — comandos 