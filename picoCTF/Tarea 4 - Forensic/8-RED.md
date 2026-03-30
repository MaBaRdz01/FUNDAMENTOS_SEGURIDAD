## RETO
RED
## DESCRIPCION
RED, RED, RED, REDDownload the image: [red.png](https://challenge-files.picoctf.net/c_verbal_sleep/831307718b34193b288dde31e557484876fb84978b5818e2627e453a54aa9ba6/red.png)
## SOLUCION
Descubrí que zsteg era una buena opción para empezar, ya que **es** una herramienta que se utiliza para **la detección de esteganografía** en **imágenes PNG y BMP** . Y dado que estamos trabajando con un archivo .PNG, pensé que sería prudente comenzar con esto.

Usando la consola web pico y el comando:

> zsteg -a red.png

Pude encontrar lo que parecía ser una cadena codificada en base64:

> “cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==”

¡Lo llevé a CyberChef para descifrarlo y encontré la bandera!

picoCTF{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}
## NOTAS ADICIONALES
zsteg **analiza imágenes** para detectar **datos ocultos** (esteganografía). Además, es capaz de extraer información oculta mediante **LSB (bit menos significativo)** y otras **técnicas esteganográficas** .


## REFERENCIAS
https://toolbox.itsec.tamu.edu/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=Y0dsamIwTlVSbnR5TTJSZk1YTmZkR2d6WDNWc2RERnROSFF6WDJOMWNqTmZaakJ5WHpVMFpHNHpOVFZmZlE9PQ