## RETO
convertme.py
## DESCRIPCION
Run the Python script and convert the given number from decimal to binary to get the flag. [Download Python script](https://artifacts.picoctf.net/c/22/convertme.py)
## SOLUCION
──(kali㉿kali)-[~/Downloads]
└─$ ls
Addadshashanammu      big-zip-files      codebook.txt  convertme.py  files      ltdis.sh  static.ltdis.strings.txt  warm
Addadshashanammu.zip  big-zip-files.zip  code.py       enc_flag      files.zip  static    static.ltdis.x86_64.txt

┌──(kali㉿kali)-[~/Downloads]
└─$ python3 convertme.py
If 91 is in decimal base, what is it in binary base?
Answer: **1011011**
That is correct! Here's your flag: **picoCTF{4ll_y0ur_b4535_762f748e}**

Se podía realizar la conversión en Cyberchef 
https://gchq.github.io/CyberChef/#recipe=From_Decimal('Space',false)To_Binary('Space',7)&input=OTE

Realice con python con bin:
>>> bin(91)
'0b1011011'
>>> 
## NOTAS ADICIONALES
Tanto python como cyberchef convierten de decimal a binario.


## REFERENCIAS
https://gchq.github.io/CyberChef/#recipe=From_Decimal('Space',false)To_Binary('Space',7)&input=OTE