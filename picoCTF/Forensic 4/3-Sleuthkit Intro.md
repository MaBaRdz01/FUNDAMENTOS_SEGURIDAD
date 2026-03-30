## RETO
Sleuthkit Intro
## DESCRIPCION
Download the disk image and use `mmls` on it to find the size of the Linux partition. Connect to the remote checker service to check your answer and get the flag.Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.[Download disk image](https://artifacts.picoctf.net/c/164/disk.img.gz)Access checker program: `nc saturn.picoctf.net 60243`
## SOLUCION
┌──(kali㉿kali)-[~/Downloads]
└─$ sudo apt install sleuthkit                      
The following packages were automatically installed and are no longer required:
  libcrypt-dev  libtsk19t64  libwireshark18  libwiretap15  libwsutil16
Use 'sudo apt autoremove' to remove them.

Upgrading:
  sleuthkit

Installing dependencies:
  libbfio1  libtsk23  libvslvm1t64

Summary:
  Upgrading: 1, Installing: 3, Removing: 0, Not Upgrading: 2046
  Download size: 1,414 kB
  Space needed: 2,844 kB / 59.2 GB available

Continue? [Y/n] yes
Get:1 http://http.kali.org/kali kali-rolling/main amd64 libbfio1 amd64 20170123-6+b3 [311 kB]
Get:2 http://us.mirror.ionos.com/linux/distributions/kali/kali kali-rolling/main amd64 libvslvm1t64 amd64 20240504-2 [422 kB]
Get:3 http://http.kali.org/kali kali-rolling/main amd64 libtsk23 amd64 4.14.0+dfsg-0kali1 [382 kB]
Get:4 http://http.kali.org/kali kali-rolling/main amd64 sleuthkit amd64 4.14.0+dfsg-0kali1 [300 kB]
92% [2 libvslvm1t64 364 kB/422 kB 86%]                              202 kB/s 0s^93% [2 libvslvm1t64 385 kB/422 kB 91%]                              202 kB/s 0s^Fetched 1,414 kB in 10s (143 kB/s)                                             
^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[BSelecting previously unselected package libbfio1:amd64.
(Reading database ... 423046 files and directories currently installed.)
Preparing to unpack .../libbfio1_20170123-6+b3_amd64.deb ...
Unpacking libbfio1:amd64 (20170123-6+b3) ...
Selecting previously unselected package libvslvm1t64:amd64.
Preparing to unpack .../libvslvm1t64_20240504-2_amd64.deb ...
Unpacking libvslvm1t64:amd64 (20240504-2) ...
Selecting previously unselected package libtsk23:amd64.
Preparing to unpack .../libtsk23_4.14.0+dfsg-0kali1_amd64.deb ...
Unpacking libtsk23:amd64 (4.14.0+dfsg-0kali1) ...
Preparing to unpack .../sleuthkit_4.14.0+dfsg-0kali1_amd64.deb ...
Unpacking sleuthkit (4.14.0+dfsg-0kali1) over (4.12.1+dfsg-0kali6) ...
Setting up libbfio1:amd64 (20170123-6+b3) ...
Setting up libvslvm1t64:amd64 (20240504-2) ...
Setting up libtsk23:amd64 (4.14.0+dfsg-0kali1) ...
Setting up sleuthkit (4.14.0+dfsg-0kali1) ...
Processing triggers for libc-bin (2.42-13) ...
Processing triggers for man-db (2.13.1-1) ...
Processing triggers for kali-menu (2025.3.2) ...
                                                                                
┌──(kali㉿kali)-[~/Downloads]
└─$ ls
Blue_bit_0.png        fixme1          home
bookshelf-pico.zip    fixme1.tar.gz   message.txt
buildings.png         fixme2          message.wav
capture.pcap          fixme2.tar.gz   myNetworkTraffic.pcap
challenge.zip         fixme3          pico_img.png
dds1-alpine.flag.img  fixme3.tar.gz   reto8
disk.img              flag.png        Tarea3_MarianaBarcenas.py~
exams_dataset.csv     fragmentos.txt  Tarea3_MarianaBarcenas.py.txt
Figure_1.png          garden.jpg      Tarea3.pdf
                                                                                
┌──(kali㉿kali)-[~/Downloads]
└─$ file disk.img 
disk.img: DOS/MBR boot sector; partition 1 : ID=0x83, active, start-CHS (0x0,32,33), end-CHS (0xc,190,50), startsector 2048, 202752 sectors
                                                                                
┌──(kali㉿kali)-[~/Downloads]
└─$ mmls disk.img 
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000204799   0000202752   Linux (0x83)
                                                                                
┌──(kali㉿kali)-[~/Downloads]
└─$  nc saturn.picoctf.net 49973
What is the size of the Linux partition in the given disk image?
Length in sectors: 202752
202752
Great work!
picoCTF{mm15_f7w!}


## NOTAS ADICIONALES

## REFERENCIAS