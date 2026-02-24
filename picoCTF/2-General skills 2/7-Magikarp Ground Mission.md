## RETO
Magikarp Ground Mission
## DESCRIPCION
Do you know how to move between directories and read files in the shell? Start the container, `ssh` to it, and then `ls` once connected to begin.Login via `ssh` as `ctf-player` with the password, `8c606eb1` on the host `wily-courier.picoctf.net` and port `55518`.
## SOLUCION
MarianaRodriguez-picoctf@webshell:~$ ==ssh  ctf-player@wily-courier.picoctf.net -p 55518==
The authenticity of host '[wily-courier.picoctf.net]:55518 ([18.189.99.27]:55518)' can't be established.
ED25519 key fingerprint is SHA256:ErlUUvYlrAxfSW1tIdzfOnGTBSr5OFkZvz0nMN4Vodw.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[wily-courier.picoctf.net]:55518' (ED25519) to the list of known hosts.
ctf-player@wily-courier.picoctf.net's password: 
Welcome to Ubuntu 18.04.6 LTS (GNU/Linux 6.14.0-1012-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage
This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.
Last login: Thu Feb 12 02:52:49 2026 from 127.0.0.1
ctf-player@pico-chall$ ==ls==
1of3.flag.txt  instructions-to-2of3.txt
ctf-player@pico-chall$ ==cat 1of3.flag.txt==
**picoCTF{xxsh_**
ctf-player@pico-chall$ ==cat instructions-to-2of3.txt==
Next, go to the root of all things, more succinctly `/`
ctf-player@pico-chall$ ==cd /==
ctf-player@pico-chall$ ==ls==
2of3.flag.txt             lib    sbin
bin                       lib64  srv
boot                      media  sys
challenge                 mnt    tmp
dev                       opt    usr
etc                       proc   var
home                      root
instructions-to-3of3.txt  run
ctf-player@pico-chall$ ==cat 2of3.flag.txt== 
**0ut_0f_//4t3r_**
ctf-player@pico-chall$ ==cat instructions-to-3of3.txt==
Lastly, ctf-player, go home... more succinctly `~`
ctf-player@pico-chall$ ==cd ~==
ctf-player@pico-chall$ ==ls==
3of3.flag.txt  drop-in
ctf-player@pico-chall$ ==cat 3of3.flag.txt==
**0b24fc4f}**

## NOTAS ADICIONALES

cat      ->Muestra contenido de un archivo.

cd /    ->Lleva a la raíz(root).

cd ~   ->Me lleva a mi carpeta(HOME).

# # REFERENCIAS

https://medium.com/@CP4rrot/picoctf-journey-magikarp-ground-mission-3b727fc2446a