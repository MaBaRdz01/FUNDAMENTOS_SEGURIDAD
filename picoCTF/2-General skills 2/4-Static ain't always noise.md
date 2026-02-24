## RETO
Static ain't always noise
## DESCRIPCION
Can you look at the data in this binary? The bash script might help![static](https://challenge-files.picoctf.net/c_wily_courier/b06384f5fdb3a6e3f0f254d1064d203e7df4bf7e9a5780a95622523367d82bc0/static), [ltdis.sh](https://challenge-files.picoctf.net/c_wily_courier/b06384f5fdb3a6e3f0f254d1064d203e7df4bf7e9a5780a95622523367d82bc0/ltdis.sh)
## SOLUCION

Solucion en STATIC
┌──(kali㉿kali)-[~]
└─$ cd /home/kali/Downloads/     
┌──(kali㉿kali)-[~/Downloads]
└─$ ls       
big-zip-files.zip  ltdis.sh  static  warm
┌──(kali㉿kali)-[~/Downloads]
└─$ file static
static: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=9a00d4dca6b92d22aa0cd1fceffa4ed7495b8534, for GNU/Linux 3.2.0, not stripped

┌──(kali㉿kali)-[~/Downloads]
└─$ strings static | grep pico
==picoCTF{d15a5m_t34s3r_20335e41}==

Si esto no funciona, se usa el otro archivo(ltdis.sh):
┌──(kali㉿kali)-[~/Downloads]
└─$ bash ltdis.sh static
Attempting disassembly of static ...
Disassembly successful! Available at: static.ltdis.x86_64.txt
Ripping strings from binary with file offsets...
Any strings found in static have been written to static.ltdis.strings.txt with file offset
┌──(kali㉿kali)-[~/Downloads]
└─$ grep "picoCTF" static.ltdis.strings.txt  
   3020 ==picoCTF{d15a5m_t34s3r_20335e41}==
## NOTAS ADICIONALES
Explicación de comandos:
==file static== -> Nos permitió ver que tipo de archivo es.

Antes de haber desensamblar o analizar código a fondo, siempre usar:

strings -> Este comando busca secuencias de caracteres imprimibles dentro de un archivo binario. En este caso ==strings static | grep pico==

si la bandera está escrita directamente en binario como constante de texto, pues aparecerá sin problema y como fue lo que paso pudimos dejarle hasta ahí y como se trata de aprender fuimos hacer el otro modo ya que a veces la bandera esta "escondida" si fuera este caso usamos el script proporcionado(ltdis.sh).

Se ejecuta el script sobre el binario:
==bash ltdis.sh static==

Esto genera dos archivos:

**static.ltdis.x86_64.txt** : Código en lenguaje ensamblador.

**static.ltdis.strings.txt** : Una lista de todos los strings encontrados en secciones especificas.

Y ahí nos fuimos sobre el archivo de strings generado:

==get "picoCTF" static.ltdis.strings.txt==
## REFERENCIAS
