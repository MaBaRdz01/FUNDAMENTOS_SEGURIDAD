## RETO
SQLiLite
## DESCRIPCION
#### Description

Can you login to this website?

Additional details will be available after launching your challenge instance.
## SOLUCION
Me acorde de un reto pasado el cual y me guie de el y prove con una variante : `' OR '1'='1` en ambos campos.

logre el **bypass de autenticación**. El servidor ejecutó la inyección y, como `'1'='1'` siempre es verdadero, me dejó pasar.

Revise el código fuente y ahí mismo salió la bandera:

`picoCTF{L00k5_l1k3_y0u_solv3d_it_9b0a4e21}`
## NOTAS ADICIONAL
Los retos pasados nos sirven de guía y mas si se documentan

## REFERENCIAS