## RETO
findme
## DESCRIPCION
Help us test the form by submiting the username as `test` and password as `test!`The website running [here](http://saturn.picoctf.net:61442/).
## SOLUCION
La pista decía "¿Hay redirecciones?". Así que inicié sesión en el sitio web y apareció este cuadro de búsqueda. Busqué algunas cadenas, pero el cuadro de búsqueda no mostró nada, así que releí la pista y empecé a trastear con Burp Suite para comprobar si había redirecciones.

Intenté iniciar sesión de nuevo y recibí la solicitud de inicio de sesión, y presioné para iniciar sesión a través de BurpSuite.

Después de presionar hacia adelante, veo una cadena interesante que parece estar codificada en base64. Esta cadena de aquí:
cGljb0NURntwcm94aWVzX2Fs

Así que intenté avanzar de nuevo y de nuevo obtuve otra cadena interesante que era una cadena codificada en base64. Esta cadena de aqui:
bF90aGVfd2F5XzNkOWUzNjk3fQ==

Junté esas cadenas y pasé a Cyberchef para decodificarlas de base64 a texto plano.
picoCTF{proxies_all_the_way_3d9e3697}
## NOTAS ADICIONALES

## REFERENCIAS
https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=Y0dsamIwTlVSbnR3Y205NGFXVnpYMkZzYkY5MGFHVmZkMkY1WHpOa09XVXpOamszZlE9PSA