## RETO
 GET aHEAD
## DESCRIPCION
Find the flag being held on this server to get ahead of the competition [http://wily-courier.picoctf.net:59332/](http://wily-courier.picoctf.net:51742/)
## SOLUCION
┌──(kali㉿kali)-[~]
└─$ curl -X HEAD http://wily-courier.picoctf.net:51742/index.php
Warning: Setting custom HTTP method to HEAD with -X/--request may not work the 
Warning: way you want. Consider using -I/--head instead.
                                                                                 
┌──(kali㉿kali)-[~]
└─$ curl -I HEAD http://wily-courier.picoctf.net:51742/index.php
curl: (6) Could not resolve host: HEAD
HTTP/1.1 200 OK
Date: Tue, 24 Feb 2026 05:35:35 GMT
Server: Apache/2.4.38 (Debian)
X-Powered-By: PHP/7.2.34
flag: picoCTF{r3j3ct_th3_du4l1ty_8b13f07}
Content-Type: text/html; charset=UTF-8
## NOTAS ADICIONALES
Tambien se podia usando Burp Suite 

Ya que te tomaste el trabajo de instalar **FoxyProxy** y **Burp Suite**:

1. **En Burp Suite:** Ve a la pestaña **Proxy** -> **Intercept** y asegúrate de que diga **Intercept is ON**.

2. **En Firefox:** Activa el perfil "Burp" en FoxyProxy y refresca la página del reto.

3. **De vuelta en Burp:** Verás la petición capturada. Verás que empieza con la palabra `GET`.

4. **El truco:** Haz clic derecho sobre el texto de la petición y selecciona **"Send to Repeater"**.

5. Ve a la pestaña **Repeater**, cambia la palabra `GET` por `HEAD` y dale al botón **Send**.

6. Revisa la respuesta a la derecha; la flag debería aparecer en los headers.
![[Pasted image 20260223234156.png]]

## REFERENCIAS