## RETO
- Sleuthkit Apprentice
## DESCRIPCION
Download this disk image and find the flag.Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download compressed disk image](https://artifacts.picoctf.net/c/136/disk.flag.img.gz)
## SOLUCION
                                                                                
┌──(kali㉿kali)-[~/Downloads]
└─$ gzip -d disk.flag.img.gz
                                                                                
┌──(kali㉿kali)-[~/Downloads]
└─$ ls           
 Blue_bit_0.png         fixme1.tar.gz    message.wav
 bookshelf-pico.zip     fixme2           myNetworkTraffic.pcap
 buildings.png          fixme2.tar.gz    pico_img.png
 capture.pcap           fixme3           reto8
 challenge.zip          fixme3.tar.gz   'reto pasadad.img'
 dds1-alpine.flag.img   flag.png         Tarea3_MarianaBarcenas.py~
 disk.flag.img          fragmentos.txt   Tarea3_MarianaBarcenas.py.txt
 exams_dataset.csv      garden.jpg       Tarea3.pdf
 Figure_1.png           home
 fixme1                 message.txt
                                                                                
┌──(kali㉿kali)-[~/Downloads]
└─$ mmls disk.flag.img      
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000360447   0000153600   Linux Swap / Solaris x86 (0x82)
004:  000:002   0000360448   0000614399   0000253952   Linux (0x83)
                                                                                
┌──(kali㉿kali)-[~/Downloads]
└─$ fls -h       
Missing image name
usage: fls [-adDFlhpruvV] [-f fstype] [-i imgtype] [-b dev_sector_size] [-m dir/] [-o imgoffset] [-z ZONE] [-s seconds] image [images] [inode]
        If [inode] is not given, the root directory is used
        -a: Display "." and ".." entries
        -d: Display deleted entries only
        -D: Display only directories
        -F: Display only files
        -l: Display long version (like ls -l)
        -i imgtype: Format of image file (use '-i list' for supported types)
        -b dev_sector_size: The size (in bytes) of the device sectors
        -f fstype: File system type (use '-f list' for supported types)
        -m: Display output in mactime input format with
              dir/ as the actual mount point of the image
        -h: Include MD5 checksum hash in mactime output
        -o imgoffset: Offset into image file (in sectors)
        -P pooltype: Pool container type (use '-P list' for supported types)
        -B pool_volume_block: Starting block (for pool volumes only)
        -S snap_id: Snapshot ID (for APFS only)
        -p: Display full path for each file
        -r: Recurse on directory entries
        -u: Display undeleted entries only
        -v: verbose output to stderr
        -V: Print version
        -z: Time zone of original machine (i.e. EST5EDT or GMT) (only useful with -l)
        -s seconds: Time skew of original machine (in seconds) (only useful with -l & -m)
        -k password: Decryption password for encrypted volumes
                                                                                
┌──(kali㉿kali)-[~/Downloads]
└─$ fls -o 360448 disk.flag.img 
d/d 451:        home
d/d 11: lost+found
d/d 12: boot
d/d 1985:       etc
d/d 1986:       proc
d/d 1987:       dev
d/d 1988:       tmp
d/d 1989:       lib
d/d 1990:       var
d/d 3969:       usr
d/d 3970:       bin
d/d 1991:       sbin
d/d 1992:       media
d/d 1993:       mnt
d/d 1994:       opt
d/d 1995:       root
d/d 1996:       run
d/d 1997:       srv
d/d 1998:       sys
d/d 2358:       swap
V/V 31745:      $OrphanFiles
                                                                                
┌──(kali㉿kali)-[~/Downloads]
└─$ fls -o 360448 disk.flag.img 1995
r/r 2363:       .ash_history
d/d 3981:       my_folder
                                                                                
┌──(kali㉿kali)-[~/Downloads]
└─$ fls -o 360448 disk.flag.img 3981
r/r * 2082(realloc):    flag.txt
r/r 2371:       flag.uni.txt
                                                                                
┌──(kali㉿kali)-[~/Downloads]
└─$ icat -o 360448 disk.flag.img 2371
picoCTF{by73_5urf3r_3497ae6b}


## NOTAS ADICIONALES
### 🔸fls

- Enumera los archivos y los nombres de los directorios en un sistema de archivos.
- Este comando mostrará el contenido del directorio, incluyendo la información de los archivos eliminados.

### 🔸icat

Muestra el contenido de un archivo en función de su número de inodo.
## REFERENCIAS
https://www.systutorials.com/docs/linux/man/1-icat/
https://wiki.sleuthkit.org/index.php/?title=Fls