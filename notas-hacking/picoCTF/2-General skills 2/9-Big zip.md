## RETO
Big zip
## DESCRIPCION
Unzip this archive and find the flag.

- [Download zip file](https://artifacts.picoctf.net/c/503/big-zip-files.zip)
## SOLUCION
┌──(kali㉿kali)-[~/Downloads]
└─$ ==ls==               
Addadshashanammu  Addadshashanammu.zip  big-zip-files  big-zip-files.zip  enc_flag  ltdis.sh  static  static.ltdis.strings.txt  static.ltdis.x86_64.txt  warm
   
┌──(kali㉿kali)-[~/Downloads]
└─$ ==cd big-zip-files==                                                                                         

┌──(kali㉿kali)-[~/Downloads/big-zip-files]
└─$ ==grep -r "picoCTF" .==
folder_pmbymkjcya/folder_cawigcwvgv/folder_ltdayfmktr/folder_fnpfclfyee/whzxrpivpqld.txt:information on the record will last a billion years. Genes and brains and books encode **picoCTF{gr3p_15_m4g1c_ef8790dc}**




## NOTAS ADICIONALES

- grep: El buscador de patrones de texto.

- -r: (Recursive) Le dice a grep que busque en todos los archivos y carpetas dentro del directorio actual.

- picoCTF": El patrón que estamos buscando (todas las flags empiezan así).
    
- . : Indica que empiece la búsqueda en el directorio donde estás parado ahora.


## REFERENCIAS

