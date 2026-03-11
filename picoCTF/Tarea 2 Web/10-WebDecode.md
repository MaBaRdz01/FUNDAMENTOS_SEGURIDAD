## RETO
WebDecode
## DESCRIPCION
Do you know how to use the web inspector?Start searching [here](http://titan.picoctf.net:50204/) to find the flag
## SOLUCION
- Se accedió al sitio web proporcionado y se navegó a través del menú principal (**Home**, **About**, **Contact**).
    
- Al inspeccionar el código fuente de la página `about.html` (usando `Ctrl + U` o la pestaña **Elements** de las DevTools), se identificó una etiqueta `<section>` con un atributo inusual llamado `notify_true`.
    
- El valor del atributo era la cadena codificada en Base64: `cGljb0NURnt3ZWJfc3VjYzNzc2Z1bGx5X2QzYzBkZWRfMjgzZTYyZmV9`
    
- Se procedió a decodificar la cadena utilizando el comando `atob()` en la consola del navegador o una herramienta de decodificación Base64.
    
- **Resultado:** `picoCTF{web_succ3ssfully_d3c0ded_283e62fe}`

## NOTAS ADICIONALES
- **Identificación de Base64:** Es fácil reconocer esta codificación porque utiliza caracteres alfanuméricos (A-Z, a-z, 0-9) y a menudo termina en uno o dos signos de igual (`=`) como relleno (padding), aunque en este caso no los necesitó.
    
- **Atributos Personalizados:** Los desarrolladores a veces usan atributos HTML no estándar (como `notify_true`) para almacenar metadatos o, en este caso, esconder información de forma superficial.

## REFERENCIAS
https://toolbox.itsec.tamu.edu/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=Y0dsamIwTlVSbnQzWldKZmMzVmpZek56YzJaMWJHeDVYMlF6WXpCa1pXUmZNamd6WlRZeVptVjk