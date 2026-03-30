## RETO
Milkslap
## DESCRIPCION
🥛
http://wily-courier.picoctf.net:52236/
## SOLUCION
Hay un archivo PNG que funciona como un GIF al mover el ratón. Básicamente, le das una bofetada a la persona de la imagen.

Al usar curl para obtener más información, no obtengo nada útil.

Luego copié el enlace de la imagen del sitio web y descargué la única imagen que había.

Y ejecuté algunas de las herramientas más comunes para esteganografía. Como se trata de un archivo PNG, utilicé el comando **zsteg** (steghide = solo JPG, zsteg = solo PNG) para intentar encontrar la bandera.

Ahora puedo leer la bandera, que está incrustada dentro del archivo png. Por supuesto, sin '\n'. Que es un salto de línea.

Bandera:
picoCTF{imag3_m4n1pul4t10n_sl4p5}
## NOTAS ADICIONALES

## REFERENCIAS