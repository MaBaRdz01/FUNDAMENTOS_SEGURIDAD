## RETO
 Glory of the Garden
## DESCRIPCION
This file contains more than it seems.Get the flag from [garden.jpg](https://challenge-files.picoctf.net/c_fickle_tempest/6013221da747114c37db29c554381dbe4bb4e746cf6bd880f9c3b5d0b495a823/garden.jpg).
## SOLUCION
Use la terminal linux y puse un comando que busca secuencias de caracteres imprimibles dentro de un archivo binario.

    strings garden.jpg | grep "picoCTF"
    
picoCTF{more_than_m33ts_the_3y339140129}

Investigue y hay mas opciones para solucionar este reto, como el usar un editor hexadecimaldonde si nos deslizamos al final del codigo se ve que los bytes que cierran el jpg, hay texto extra 

       xxd garden.jpg | tail -n 20

Si no queremos usar la terminal, podemos subir la imagen a un sitio como **Aperi'Solve** o un **Hex Editor Online**. Buscar en la columna de texto a la derecha, al final de todo el archivo.
## NOTAS ADICIONALES
Se utilizó el comando `strings` debido a su eficacia para extraer secuencias de caracteres imprimibles de archivos binarios. Al filtrar la salida con grep, se optimizó la búsqueda de la cadena específica del formato de la competencia, demostrando que la información no estaba cifrada ni comprimida, sino simplemente oculta en texto plano
## REFERENCIAS
https://medium.com/@sobatistacyber/picoctf-writeup-glory-of-the-garden-6e0e23173eba