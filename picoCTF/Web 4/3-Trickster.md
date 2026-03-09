## RETO
### Trickster
## DESCRIPCION
I found a web app that can help process images: PNG images only!

Additional details will be available after launching your challenge instance.
## SOLUCION
Para resolver este reto, se siguieron los siguientes pasos técnicos:

1. **Evasión de Filtros de Subida:** * Se creó un archivo con la extensión doble `.png.php` para engañar al servidor y que permitiera la ejecución de código PHP mientras se "disfrazaba" de imagen.
    
    - Se añadió la cabecera de bytes mágicos `PNG` al inicio del archivo para que el sistema de detección de tipos de archivos lo identificara como una imagen válida.
        
2. **Despliegue de Web Shell:**
    
    - Se subió un script en PHP diseñado para recibir comandos a través de parámetros URL

3. **Exploración del Sistema:**
    
    - Utilizando el comando `ls ..`, se listaron los archivos en el directorio superior del servidor.
        
    - Se identificó un archivo con nombre aleatorio: `MQZWCYZWGI2WE.txt`.
        
4. **Exfiltración de la Bandera:**
    
    - Se ejecutó el comando `cat ../MQZWCYZWGI2WE.txt` para leer el contenido del archivo y obtener la cadena `picoCTF{...}`.

## NOTAS ADICIONALES
- **Importancia de los Magic Bytes:** El servidor no solo revisa la extensión, sino los primeros bytes del archivo. Sin la palabra `PNG` al inicio, el archivo sería rechazado aunque tuviera la extensión correcta.

- **Configuración del Servidor:** Este ataque fue posible porque el servidor Apache/Nginx estaba configurado para procesar archivos `.php` incluso si tenían otra extensión previa en el nombre.
## REFERENCIAS
