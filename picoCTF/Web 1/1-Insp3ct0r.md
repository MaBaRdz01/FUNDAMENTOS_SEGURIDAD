## RETO
Insp3ct0r
## DESCRIPCION
Kishor Balan tipped us off that the following code may need inspection:http://fickle-tempest.picoctf.net:53524

## SOLUCION
1. Ir al link:http://fickle-tempest.picoctf.net:53524
2. Dar clic derecho en cualquier parte de la pagina y seleccionar **Inspector** para abrir la herramienta de desarrollo del navegador.
![[Pasted image 20260223122929.png]]
A primera vista, al inspeccionarla, tenemos la primera bandera:
![[Pasted image 20260223123119.png]]
3. En la sección de fuentes, se encuentran tres archivos que podrían contener las otras dos banderas que faltan:
![[Pasted image 20260223123335.png]]
myjs.js y mycss.css
4. checaremos myjs.js  y a simple vista se ve la 3er bandera comentada:
![[Pasted image 20260223123534.png]]

5.  ahora checamos el mycss.css y a simple vista tambien se ve la bandera:
![[Pasted image 20260223123645.png]]
picoCTF{tru3_d3t3ct1ve_0r_ju5t _lucky?302945a7}

## NOTAS ADICIONALES
Este desafío es un gran recordatorio de que, a veces, **basta con inspeccionar el código del lado del cliente** . No todas las tareas de CTF requieren explotación: la observación y la curiosidad son herramientas poderosas.

## REFERENCIAS
