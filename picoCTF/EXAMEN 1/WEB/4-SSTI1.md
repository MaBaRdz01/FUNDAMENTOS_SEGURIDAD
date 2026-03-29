## RETO
 SSTI1
## DESCRIPCION
## SOLUCION
Una vez iniciada la instancia, se me presentó una aplicación de una sola página con un único campo de entrada y un botón.

El objetivo era claro: identificar el motor de plantillas en uso.

Comencé enviando una expresión aritmética simple usando llaves dobles, como por ejemplo `{{7*7}}`: . Cuando la aplicación devolvió `49`, confirmó la presencia de una vulnerabilidad de inyección de plantillas del lado del servidor (SSTI), probablemente utilizando el motor de plantillas Jinja2.

Una vez confirmado esto, el siguiente paso fue diseñar una carga útil adecuada para explotar la vulnerabilidad y recuperar la bandera.

Ahora necesitamos inyectar una carga útil que nos permita ejecutar comandos en el servidor, para así poder ver qué archivos están disponibles.

{{ __import__('os').popen('ls').read() }}

Dado que nuestra carga útil inicial está siendo bloqueada por el filtro del servidor, necesitamos hacer que sea más complejo eludir el filtro.

Añadimos esta función `request.application.__globals__.__builtins__`porque nuestro código original `__import__('os')`estaba bloqueado por un filtro. Para sortearlo, necesitábamos una ruta diferente para acceder indirectamente a las funciones integradas de Python.

Nuestra carga útil funcionó correctamente, lo que significa que pudimos ejecutar comandos en el servidor. Ahora, el último paso es leer el contenido del `flag`archivo para resolver el desafío.

Para ello utilizaremos la siguiente carga útil:

{{ request.application.__globals__.__builtins__.__import__( 'os' ). popen ( 'cat flag' ). read () }}

¡Aquí está nuestra bandera!
picoCTF{s4rv3r_s1d3_t3mp14t3_1nj3ct10n5_4r3_c001_09365533}
## NOTAS ADICIONALES
### Así es como funciona la cadena:

1. `**request.application**`  
    En Flask, el `request`objeto nos da acceso a la instancia de la aplicación a través de `request.application`.
2. `**__globals__**`  
    La aplicación (a menudo una función u objeto) almacena referencias a sus variables globales mediante el `__globals__`atributo. Esto nos da acceso al ámbito interno de Python.
3. `**__builtins__**`  
    Dentro de `__globals__`, hay `__builtins__`, que contiene todas las funciones integradas de Python, incluyendo`__import__`
## REFERENCIAS