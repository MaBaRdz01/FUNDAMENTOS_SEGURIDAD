## RETO
repetitions
## DESCRIPCION
Can you make sense of this file?Download the file [here](https://artifacts.picoctf.net/c/476/enc_flag).
## SOLUCION
┌──(kali㉿kali)-[~/Downloads]
└─$ ==ls==
Addadshashanammu      ltdis.sh                  static.ltdis.x86_64.txt
Addadshashanammu.zip  static                    warm
enc_flag              static.ltdis.strings.txt

┌──(kali㉿kali)-[~/Downloads]
└─$ ==cat enc_flag==                   
VmpGU1EyRXlUWGxTYmxKVVYwZFNWbGxyV21GV1JteDBUbFpPYWxKdFVsaFpWVlUxWVZaS1ZWWnVh
RmRXZWtab1dWWmtSMk5yTlZWWApiVVpUVm10d1VWZFdVa2RpYlZaWFZtNVdVZ3BpU0VKeldWUkNk
MlZXVlhoWGJYQk9VbFJXU0ZkcVRuTldaM0JZVWpGS2VWWkdaSGRXCk1sWnpWV3hhVm1KRk5XOVVW
VkpEVGxaYVdFMVhSbFZrTTBKVVZXMTRWMDVHV2toalJYUlhDazFyV25sVVZXaHpWakpHZEdWRlZs
aGkKYlRrelZERldUMkpzUWxWTlJYTkxDZz09Cg==

==QUIERO AGREGAR QUE EN ESTA PARTE CUANDO ABRES EL DOCUMENTO Y ENCUENTAS UN TEXTO COMO EL DE ARRIBA Y TIENE UNA TERMINACION DE ==  O = SUELE SER PORQUE ESTA EN BASE64==

┌──(kali㉿kali)-[~/Downloads]
└─$ ==cat enc_flag | base64 -d | base64 -d | base64 -d== 
WTBkc2FtSXdUbFZTYm5ScFdWaE9iRTVxVW1aaWFrNTZaRVJPYTFneVVuQlpla0pyU1ZjME5GZ3lV
WGRrTWpWelRVUlNhMDB5VW1aTwpSRlV4VGpKV2FrMHlWamxEWnowOUNnPT0K

┌──(kali㉿kali)-[~/Downloads]
└─$ ==cat enc_flag | base64 -d | base64 -d | base64 -d |base64 -d | base64 -d | base64 -d==
**picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_4557ec3e}**


## NOTAS DICIONALES
TAMBIEN SE PODIA EN CYBERCHEF

SIGNIFICADO DE NUEVOS COMANDOS:
- cat enc_flag: Para ver el contenido.

- base64 -d: Para decodificar una capa
- "pipes" (`|`) para pasar el resultado de un comando al siguiente



## REFERENCIAS
https://toolbox.itsec.tamu.edu/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)From_Base64('A-Za-z0-9%2B/%3D',true,false)From_Base64('A-Za-z0-9%2B/%3D',true,false)From_Base64('A-Za-z0-9%2B/%3D',true,false)From_Base64('A-Za-z0-9%2B/%3D',true,false)From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=Vm1wR1UxRXlSWGxVV0d4VFlteEtWVll3WkZOV2JHeHlWMjFHVjFKdGVEQlViRnBQWVd4S2RGVnNhRnBXVmxVeFdWWmFTMVpXV25WaApSbVJYWld0YWIxZFdXbXRTTWs1eVRsWldXQXBpVlZwVVZtMTBkMVZXWkZkVmEyUnBZbFphV0ZadE5WZFZaM0JwVTBWS2VsZFdVa05rCk1sWlhWbGhvV0dKWVFrOVZiRkpYVTBaa2NWUnVUbGRhTTBKWlZXcEdTMlZXV2tkYVNHUlhDazFzV25wV1YzaGhWbTFLUms1WE9WVlcKVmtwRVZHeGFZVmRGTVZoU2JGWnJUVEJLVlZaWE1UUldNRFZIVjJ0b2FsSllVbGhEYXpGeVYyNXNWVlpYYUhwV2FrcEhaRWRXUmxacwphR2tLWWxScmVsWkVSbGRVTWtwelVXeFdUbEpZVGt4RFp6MDlDZz09
