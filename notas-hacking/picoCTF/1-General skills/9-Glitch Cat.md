## RETO
Glitch Cat
## DESCRIPCION
Our flag printing service has started glitching!

Additional details will be available after launching your challenge instance.
## SOLUCION
Descargamos python y procedemos:
`┌──(kali㉿kali)-[~]`
`└─$ nc saturn.picoctf.net 65360`  
`'picoCTF{gl17ch_m3_n07_' + chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) + chr(0x61) + chr(0x34) + chr(0x35) + chr(0x64) + '}'`
                     
`┌──(kali㉿kali)-[~]`
`└─$ python3`                     
`Python 3.13.7 (main, Aug 20 2025, 22:17:40) [GCC 14.3.0] on linux`
`Type "help", "copyright", "credits" or "license" for more information.`
>>> `'picoCTF{gl17ch_m3_n07_' + chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) + c\`
`hr(0x61) + chr(0x34) + chr(0x35) + chr(0x64) + '}'`
`'picoCTF{gl17ch_m3_n07_9c42a45d}'`
>>> 

## NOTAS ADICIONALES
La bandera estaba fallando porque estaba código ya sea Hexa o decimal y pues Python ayudo a volverlo a las características correspondientes en código ASCII
## REFERENCIAS
Python, Linux.
https://medium.com/@elitere.solutions20/picoctf-glitch-cat-b89b9f50afdb
