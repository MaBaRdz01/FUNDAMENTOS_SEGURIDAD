## RETO
- Disk, disk, sleuth!
## DESCRIPCION
Use `srch_strings` from the sleuthkit and some terminal-fu to find a flag in this disk image.[dds1-alpine.flag.img.gz](https://challenge-files.picoctf.net/c_wily_courier/27cbd6a2ed4a59d600f2a24c1ccaa6de66f9aeee95d6b365160fd75649e45f1b/dds1-alpine.flag.img.gz)
## SOLUCION
┌──(kali㉿kali)-[~/Downloads]
└─$ gunzip dds1-alpine.flag.img.gz  
                                                                                
┌──(kali㉿kali)-[~/Downloads]
└─$ sudo apt install autopsy 
[sudo] password for kali: 
autopsy is already the newest version (2.24-6kali1).
autopsy set to manually installed.
The following packages were automatically installed and are no longer required:
  libcrypt-dev  libwireshark18  libwiretap15  libwsutil16
Use 'sudo apt autoremove' to remove them.

Summary:
  Upgrading: 0, Installing: 0, Removing: 0, Not Upgrading: 2047
                                                                                
┌──(kali㉿kali)-[~/Downloads]
└─$ srch_strings dds1-alpine.flag.img | grep picoCTF
  SAY picoCTF{f0r3ns1c4t0r_n30phyt3_5e56e786}


## NOTAS ADICIONALES

## REFERENCIAS