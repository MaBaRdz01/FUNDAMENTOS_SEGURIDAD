## RETO
Tab, Tab, Attack
## DESCRIPCION
Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames. [Addadshashanammu.zip](https://challenge-files.picoctf.net/c_wily_courier/ce53ef9432bf367be41e465224d721c1187c39debcd758efcd28e99a6b7ff7a4/Addadshashanammu.zip)
## SOLUCION
┌──(kali㉿kali)-[~/Downloads]
└─$ ==unzip Addadshashanammu.zip==
Archive:  Addadshashanammu.zip
   creating: Addadshashanammu/
   creating: Addadshashanammu/Almurbalarammi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
 extracting: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet.c  
  inflating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet  

┌──(kali㉿kali)-[~/Downloads]
└─$ ==cd== Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku 

┌──(kali㉿kali)-[~/…/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└─$ ==ls==
fang-of-haynekhtnamet  fang-of-haynekhtnamet.c

┌──(kali㉿kali)-[~/…/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└─$ ==chmod +x fang-of-haynekhtnamet==    
  
┌──(kali㉿kali)-[~/…/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└─$ ==./fang-of-haynekhtnamet== 
*ZAP!* **picoCTF{l3v3l_up!_t4k3_4_r35t!_fc588427}**
## NOTAS ADICIONALES
unzip -> nos ayuda a descomprimir
convierte un archivo normal en un 

chmod +x  -> convierte un archivo normal en un programa ejecutable.

- chmod: Es la abreviatura de _Change Mode_ (Cambiar modo). Se usa para modificar los permisos de acceso a un archivo o directorio.
- x: El signo `+` indica que vas a **agregar** un permiso, y la `x` representa **eXecutable**.
## REFERENCIAS
https://medium.com/@Iampreth/ctf-writeups-tab-tab-attack-70fabe73f8eb

