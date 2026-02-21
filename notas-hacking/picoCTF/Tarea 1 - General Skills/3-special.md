## RETO
special
## DESCRIPCION
Don't power users get tired of making spelling mistakes in the shell? Not anymore! Enter Special, the Spell Checked Interface for Affecting Linux. Now, every word is properly spelled and capitalized... automatically and behind-the-scenes! Be the first to test Special in beta, and feel free to tell us all about how Special streamlines every development process that you face. When your co-workers see your amazing shell interface, just tell them: That's Special (TM)Start your instance to see connection details.`ssh -p 57505 ctf-player@saturn.picoctf.net`The password is `af86add3`
## SOLUCION

Se accedió al servidor remoto proporcionado por picoCTF mediante una sesión interactiva de shell restringida. Durante la exploración inicial se observó que los comandos tradicionales de Linux (`ls`, `echo`, `clear`, etc.) no se ejecutaban correctamente.

Al intentar ejecutar comandos básicos, el sistema devolvía errores como:

sh: 1: Is: not found  
sh: 1: Echo: not found

Esto indicó la presencia de un mecanismo de filtrado o modificación automática de comandos. En particular, se detectó que el entorno alteraba la entrada del usuario, modificando palabras clave antes de su ejecución.

Debido a estas restricciones, se optó por emplear técnicas de evasión utilizando expansión de parámetros en Bash. Se utilizó la sintaxis:

==${parametro=ls blargh}==

Esta construcción permitió que el shell realizara la expansión y asignación del parámetro antes de la validación o transformación aplicada por el sistema. Como resultado, el comando `ls blargh` fue interpretado correctamente, mostrando el contenido del directorio:

flag.txt

Posteriormente, se aplicó un enfoque similar para acceder al archivo de la bandera. Finalmente, el sistema reveló la flag:

**picoCTF{5p311ch3ck_15_7h3_w0r57_6a2763f6}**

## NOTAS ADICIONALES

- El entorno presentaba un filtro que modificaba comandos comunes, simulando un comportamiento similar a un autocorrector o _spellcheck_.

- La alteración de comandos impedía el uso irecto de utilidades básicas del sistema.

- Se comprobó que rutas absolutas (`/bin/ls`, `/usr/bin/ls`) también estaban bloqueadas.

- La solución consistió en aprovechar el orden de evaluación del shell, específicamente la expansión de parámetros.

- El reto enfatiza la importancia de comprender cómo Bash procesa variables y expansiones antes de ejecutar comandos.

## REFERENCIAS
https://josephkimiri.github.io/posts/Special/