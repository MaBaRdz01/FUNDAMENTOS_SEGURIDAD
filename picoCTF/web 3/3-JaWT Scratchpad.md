## RETO
JaWT Scratchpad
## DESCRIPCION
Check the admin scratchpad! http://fickle-tempest.picoctf.net:51651
## SOLUCION
- Se inició sesión con cualquier usuario para obtener un JWT almacenado en la cookie del navegador.

- Se inspeccionó el token y se analizó el comportamiento del servidor.

- Al provocar un error, el servidor mostró el siguiente fragmento de código:

jwt.decode(cookie, 'ilovepico')

- Esto reveló que la clave secreta utilizada para firmar los tokens era:

ilovepico

- Se generó un nuevo JWT con el siguiente payload:

{  
 "user": "admin"  
}

Usando:

 Secret: ilovepico


picoCTF{jawt_was_just_what_you_thought_bbb82bd4a57564aefb32d69dafb60583}
## NOTAS ADICIONALES
- El error del servidor expuso información sensible (la clave secreta).

- Una mala gestión de excepciones puede comprometer completamente la seguridad.

- JWT debe manejarse cuidadosamente para evitar filtraciones de secretos.

## REFERENCIAS
https://www.jwt.io/