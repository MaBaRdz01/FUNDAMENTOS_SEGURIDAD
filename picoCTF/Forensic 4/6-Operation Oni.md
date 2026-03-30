## RETO
- Operation Oni
## DESCRIPCION
Download this disk image, find the key and log into the remote machine.Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download disk image](https://artifacts.picoctf.net/c/71/disk.img.gz)
- Remote machine: `ssh -i key_file -p 60307 ctf-player@saturn.picoctf.net`
## SOLUCION

Después de descargar el archivo usando **wget,** descomprímalo usando **gunzip** y luego verifique el tipo de archivo.

Luego, al verificar las particiones de archivos usando el comando **mmls** , se encontraron tres particiones, de las cuales una no estaba asignada.

Pulsa Intro o haz clic para ver la imagen a tamaño completo.

Luego buscó el sistema de archivos de la partición número 2 **(Linux 0x83)** usando el comando **fsstat.**

La primera partición es una partición basada en Linux, así que busqué los archivos y directorios de esta partición usando el comando **fls** .

Luego verifiqué el sistema de archivos de la partición número 3 ( **Linux 0x83** ) usando el comando **fsstat** y descubrí que también se trata de una partición Linux.

Luego buscó los directorios y archivos usando el comando **fls.**

![[Pasted image 20260329200557.png|247]]

Luego, después de mirar en el directorio ssh...

Pulsa Intro o haz clic para ver la imagen a tamaño completo.

![](https://miro.medium.com/v2/resize:fit:700/1*ejQAVCBErBlIQWog0SLtQQ.png)

Se encontraron la clave pública y la clave privada.

Leyendo cada archivo uno por uno

Pulsa Intro o haz clic para ver la imagen a tamaño completo.

![](https://miro.medium.com/v2/resize:fit:700/1*8enLWtZrHTs8cqfUgy73hg.png)

Luego exporté el archivo a mi máquina local usando **icat.**

Pulsa Intro o haz clic para ver la imagen a tamaño completo.

![](https://miro.medium.com/v2/resize:fit:700/1*Apz4MH94tvUeaLKXHMBtpg.png)

Se verificó el permiso de la clave privada usando **ls -l.**

Pulsa Intro o haz clic para ver la imagen a tamaño completo.

![](https://miro.medium.com/v2/resize:fit:700/1*6kfMwHJMmCkJ1bht0lomlA.png)

Luego, cambiar los permisos de la clave privada.

Así que después de cambiar los permisos de la clave privada usando el comando **chmod**

Ahora inicie sesión en ssh usando la clave privada a través de `ssh -i key_file -p 60307 ctf-player@saturn.picoctf.net`

Luego, tras revisar los directorios, encontró la bandera.

picoCTF{k3y_5l3u7h_af277f77}
## NOTAS ADICIONALES

## REFERENCIAS