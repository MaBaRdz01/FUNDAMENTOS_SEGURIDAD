## RETO
Secrets
## DESCRIPCION
We have several pages hidden. Can you find the one with the flag?

Additional details will be available after launching your challenge instance.
## SOLUCION
Ver código fuente de la página 

Busca etiquetas `<link>` o rutas en el HTML. Se verá que el sitio carga archivos desde una carpeta específica, usualmente llamada `/secret/`.

Paso 2: 

El nombre del reto es "Secrets" (en plural), lo que sugiere que hay varios niveles de carpetas. La clave aquí es ir navegando manualmente o mediante fuerza bruta por los subdirectorios:

1. **Primer nivel:** Navega a `http://saturn.picoctf.net:51710//secret/`
        
2. **Segundo nivel:** En el código de `/secret/`, se encontrará una referencia a otra carpeta, por ejemplo `/secret/hidden/`.
    
    - Navega a `http://saturn.picoctf.net:51710//secret/hidden/`
        
3. **Tercer nivel:** Se repite el proceso. Buscamos en el código fuente de esa nueva página hasta encontrar una ruta como `/secret/hidden/superhidden/`.
4. Localizar la bandera

Eventualmente, llegarás a una carpeta que contiene un archivo .css y hay un código donde se le cambia el color y muestra la bandera. 
`picoCTF{succ3ss_@h3n1c@10n_51b260fe}`
## NOTAS ADICIONALES

## REFERENCIAS