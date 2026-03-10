## RETO
Inspect HTML
## DESCRIPCION
Can you get the flag?Go to this [website](http://saturn.picoctf.net:64383/) and see what you can discover.
## SOLUCION
#### 1. Abrir el sitio del reto

#### 2. Usar el Inspector o Ver Código Fuente


- Presiona `Ctrl + U`. Esto abrirá una pestaña nueva con el código HTML puro. Buscamos comentarios que resalten en color diferente (normalmente verde o gris) y que empiecen con ``).
    
    - Se localizó la bandera completa oculta dentro de un comentario en el cuerpo del documento.



## NOTAS ADICIONALES
Este reto demuestra que los comentarios en HTML son visibles para cualquier usuario final y nunca deben usarse para documentar información sensible o contraseñas.
## REFERENCIAS