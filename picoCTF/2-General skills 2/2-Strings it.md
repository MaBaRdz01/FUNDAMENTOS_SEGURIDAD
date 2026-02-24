## RETO
Strings it
## DESCRIPCION
Can you find the flag in [file](https://challenge-files.picoctf.net/c_fickle_tempest/fd00e7cc9b263f22c323572d2d5fc37d170f8e58e99a91f8991d0f07c69b21ff/strings) without running it?
## SOLUCION
1.copiamos la dirección del enlace
https://challenge-files.picoctf.net/c_fickle_tempest/fd00e7cc9b263f22c323572d2d5fc37d170f8e58e99a91f8991d0f07c69b21ff/strings

2.usamos el comando wget para descargar el archivo a la instancia shell 
MarianaRodriguez-picoctf@webshell:~$ wget https://challenge-files.picoctf.net/c_fickle_tempest/fd00e7cc9b263f22c323572d2d5fc37d170f8e58e99a91f8991d0f07c69b21ff/strings
.
.
.
.
3.Ver el tipo de archivo:
MarianaRodriguez-picoctf@webshell:~$ file strings

4.probar si con cat podemos ver que hay dentro del archivo y se ve muchas cosas pero no se ve claramente una bandera o algo relacionado(parece un texto absurdo)

5.Como sabemos que la llave empieza con pico, vamos a canalizar la salida anterior, usando el comando grep:
MarianaRodriguez-picoctf@webshell:~$  strings strings | grep pico
picoCTF{5tRIng5_1T_FB7D7Bb6}

## NOTAS ADICIONALES
 ==strings strings | grep pico==
 ### El Desglose del Comando

1. strings(el ejecutable): Es una herramienta que busca y muestra las secuencias de caracteres imprimibles (texto legible) dentro de un archivo binario.
    
2. strings (el argumento): En tu ejemplo, le estás pidiendo al programa que analice a _sí mismo_ (el archivo ejecutable de la herramienta strings).
    
3. |(el pipe): Toma la salida del primer comando y se la pasa como entrada al segundo.
    
4. grep pico: Filtra todos los resultados y solo muestra las líneas que contengan la palabra "pico".
## REFERENCIAS
Terminal shell de pico 
