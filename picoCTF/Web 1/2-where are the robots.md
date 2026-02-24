## RETO
Where are the robots
## DESCRIPCION
Can you find the robots?http://fickle-tempest.picoctf.net:60181
## SOLUCION
Accedo al archivo robots.txt añadiendo "/robots.txt" a la URL del sitio. Esto es lo que obtengo:
![[Pasted image 20260223144558.png]]
Ahora me concentro en la parte "Disallow" del archivo. Es una extensión HTML, lo que significa que debería dirigir a otra página web. Añado **"/cc6b1.html"** a la URL del sitio y ¡listo! Aquí está la bandera.
![[Pasted image 20260223144717.png]]
## NOTAS ADICIONALES
Un archivo _robots.txt_ en un sitio web funcionará como una petición que especifica que determinados robots no hagan caso a [archivos](https://es.wikipedia.org/wiki/Archivo_\(inform%C3%A1tica\) "Archivo (informática)") o [directorios](https://es.wikipedia.org/wiki/Directorio "Directorio") específicos en su búsqueda.

## REFERENCIAS
https://es.wikipedia.org/wiki/Est%C3%A1ndar_de_exclusi%C3%B3n_de_robots