## RETO
hideme
## DESCRIPCION
Every file gets a flag.The SOC analyst saw one image been sent back and forth between two people. They decided to investigate and found out that there was more than what meets the eye [here](https://artifacts.picoctf.net/c/258/flag.png).
## SOLUCION

## **Paso 1: Comprobar el tipo de archivo**

Comencé por identificar el formato del archivo:

**Salida:** “flag.png: datos de imagen PNG, 512 x 504, RGBA de 8 bits/color, no entrelazado”

Entonces, es una imagen PNG.

## **Paso 2: Inspeccionar la imagen**

No apareció nada inusual, solo una imagen normal (el logo de picoCTF). Eso significa que la bandera podría estar incrustada dentro.

## **Paso 3: Analizando más a fondo con el volcado hexadecimal**
Al desplazarme hacia abajo, noté algo sospechoso: había referencias a secret/ y flag.png dentro del archivo PNG.

Esto sugiere que podría haber un **archivo ZIP** incrustado dentro del archivo PNG.

## **Paso 4: Extracción de archivos ocultos con binwalk**

Para confirmar, utilicé binwalk con extracción
La salida mostró datos de archivo ZIP con archivos dentro de 'secret'.

## **Paso 5: Recuperar la bandera oculta**

La extracción creó un directorio (_flag.png.extracted/) que contiene otro archivo.

Encontré otro archivo llamado flag.png, al abrirlo se reveló la bandera oculta:

picoCTF{Hiddinng_An_imag3_within_@n_ima9e_d55982e8}
## NOTAS ADICIONALES

## REFERENCIAS