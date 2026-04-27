## RETO
c0rrupt
## DESCRIPCION
Encontramos este [archivo](https://challenge-files.picoctf.net/c_fickle_tempest/87bdc8ce30b177d033b3d68bca4647950bb07304032861baa912ebe08701d355/mystery) . Recupera la bandera.
## SOLUCION
1. Al revisarlo `file mystery`no se indica nada. Sin embargo, al ver `head`el archivo misterioso se observa que parece una imagen PNG:
    
    Copiar
    
    ```
     $ xxd -g 1 mystery | head
     00000000: 89 65 4e 34 0d 0a b0 aa 00 00 00 0d 43 22 44 52  .eN4........C"DR
     00000010: 00 00 06 6a 00 00 04 47 08 02 00 00 00 7c 8b ab  ...j...G.....|..
     00000020: 78 00 00 00 01 73 52 47 42 00 ae ce 1c e9 00 00  x....sRGB.......
     00000030: 00 04 67 41 4d 41 00 00 b1 8f 0b fc 61 05 00 00  ..gAMA......a...
     00000040: 00 09 70 48 59 73 aa 00 16 25 00 00 16 25 01 49  ..pHYs...%...%.I
     00000050: 52 24 f0 aa aa ff a5 ab 44 45 54 78 5e ec bd 3f  R$......DETx^..?
     00000060: 8e 64 cd 71 bd 2d 8b 20 20 80 90 41 83 02 08 d0  .d.q.-.  ..A....
     00000070: f9 ed 40 a0 f3 6e 40 7b 90 23 8f 1e d7 20 8b 3e  ..@..n@{.#... .>
     00000080: b7 c1 0d 70 03 74 b5 03 ae 41 6b f8 be a8 fb dc  ...p.t...Ak.....
     00000090: 3e 7d 2a 22 33 6f de 5b 55 dd 3d 3d f9 20 91 88  >}*"3o.[U.==. ..
    ```
    
2. La [especificación PNG](https://www.w3.org/TR/2003/REC-PNG-20031110/) indica que la [firma PNG](https://www.w3.org/TR/2003/REC-PNG-20031110/#5PNG-file-signature) (los primeros ocho bytes de un flujo de datos PNG) debe ser `137 80 78 71 13 10 26 10`(decimal) o `89 50 4E 47 0D 0A 1A 0A`(hexadecimal).
    
3. Así que vamos a reemplazar la firma usando [un editor hexadecimal](https://hexed.it/) :
    
    Copiar
    
    ```
     $ xxd -g 1 mystery.png | head
     00000000: 89 50 4e 47 0d 0a 1a 0a 00 00 00 0d 43 22 44 52  .PNG........C"DR
     00000010: 00 00 06 6a 00 00 04 47 08 02 00 00 00 7c 8b ab  ...j...G.....|..
     00000020: 78 00 00 00 01 73 52 47 42 00 ae ce 1c e9 00 00  x....sRGB.......
     00000030: 00 04 67 41 4d 41 00 00 b1 8f 0b fc 61 05 00 00  ..gAMA......a...
     00000040: 00 09 70 48 59 73 aa 00 16 25 00 00 16 25 01 49  ..pHYs...%...%.I
     00000050: 52 24 f0 aa aa ff a5 ab 44 45 54 78 5e ec bd 3f  R$......DETx^..?
     00000060: 8e 64 cd 71 bd 2d 8b 20 20 80 90 41 83 02 08 d0  .d.q.-.  ..A....
     00000070: f9 ed 40 a0 f3 6e 40 7b 90 23 8f 1e d7 20 8b 3e  ..@..n@{.#... .>
     00000080: b7 c1 0d 70 03 74 b5 03 ae 41 6b f8 be a8 fb dc  ...p.t...Ak.....
     00000090: 3e 7d 2a 22 33 6f de 5b 55 dd 3d 3d f9 20 91 88  >}*"3o.[U.==. ..
    ```
    
4. Tras el encabezado, se presenta una serie de bloques. Cada bloque comienza con 4 bytes que indican su longitud, 4 bytes que especifican su tipo, el contenido del bloque (con la longitud declarada previamente) y 4 bytes de suma de verificación. Consulte la sección "5.3 Estructura de los bloques" de [esta página](https://www.w3.org/TR/2003/REC-PNG-20031110/#5Chunk-layout) para obtener más información.
    
5. El primer fragmento se llama `IHDR`y tiene una longitud de `0xD`, por lo que sabemos que los siguientes 8 bytes son `00 00 00 0D 49 48 44 52`(hexadecimal):
    
    Copiar
    
    ```
     $ xxd -g 1 mystery.png | head
     00000000: 89 50 4e 47 0d 0a 1a 0a 00 00 00 0d 49 48 44 52  .PNG........IHDR
     00000010: 00 00 06 6a 00 00 04 47 08 02 00 00 00 7c 8b ab  ...j...G.....|..
     00000020: 78 00 00 00 01 73 52 47 42 00 ae ce 1c e9 00 00  x....sRGB.......
     00000030: 00 04 67 41 4d 41 00 00 b1 8f 0b fc 61 05 00 00  ..gAMA......a...
     00000040: 00 09 70 48 59 73 aa 00 16 25 00 00 16 25 01 49  ..pHYs...%...%.I
     00000050: 52 24 f0 aa aa ff a5 ab 44 45 54 78 5e ec bd 3f  R$......DETx^..?
     00000060: 8e 64 cd 71 bd 2d 8b 20 20 80 90 41 83 02 08 d0  .d.q.-.  ..A....
     00000070: f9 ed 40 a0 f3 6e 40 7b 90 23 8f 1e d7 20 8b 3e  ..@..n@{.#... .>
     00000080: b7 c1 0d 70 03 74 b5 03 ae 41 6b f8 be a8 fb dc  ...p.t...Ak.....
     00000090: 3e 7d 2a 22 33 6f de 5b 55 dd 3d 3d f9 20 91 88  >}*"3o.[U.==. ..
    ```
    
6. Ahora el archivo se identifica como un archivo PNG:
    
    Copiar
    
    ```
     $ file fixed.png
     fixed.png: PNG image data, 1642 x 1095, 8-bit/color RGB, non-interlaced
    ```
    
7. `pngcheck`Enumera dos errores más que deben resolverse:
    
    Copiar
    
    ```
     pngcheck -vf mystery.png
     File: mystery.png (202940 bytes)
     chunk IHDR at offset 0x0000c, length 13
         1642 x 1095 image, 24-bit RGB, non-interlaced
     chunk sRGB at offset 0x00025, length 1
         rendering intent = perceptual
     chunk gAMA at offset 0x00032, length 4: 0.45455
     chunk pHYs at offset 0x00042, length 9: 2852132389x5669 pixels/meter
     CRC error in chunk pHYs (computed 38d82c82, expected 495224f0)
     :  invalid chunk length (too large)
    ```
    
    Necesitamos corregir el error CRC (suma de verificación) en el fragmento `pHYs`y encontrar un fragmento con una longitud no válida.
    
8. El error CRC significa que la suma de verificación (valor CRC) o los datos están dañados. Para solucionar este error en el fragmento, `pHYs`podemos simplemente reemplazar el valor CRC (esperado) con el valor calculado. La sección CRC sirve para comprobar si los datos están dañados. Esencialmente, es una suma de verificación de ese fragmento. Si bien reemplazar el CRC funciona, el método más correcto es corregir el contenido `pHYs`para obtener el mismo CRC y así solucionar el problema. La siguiente tabla muestra la estructura del `pHYs`fragmento:
    
    Nombre
    
    Longitud
    
    Valor actual
    
    Píxeles por unidad, eje X
    
    4 bytes (entero sin signo PNG)
    
    aa 00 16 25
    
    Píxeles por unidad, eje Y
    
    4 bytes (entero sin signo PNG)
    
    00 00 16 25
    
    especificador de unidad
    
    1 byte
    
    01
    
    Dado que los píxeles por unidad difieren en tan solo un byte, y el `0xaa`valor para el eje X es muy grande, tiene sentido colocar un cero en su lugar. Esto corrige la suma de verificación.
    
    Copiar
    
    ```
     $ xxd -g 1 mystery.png | head
     00000000: 89 50 4e 47 0d 0a 1a 0a 00 00 00 0d 49 48 44 52  .PNG........IHDR
     00000010: 00 00 06 6a 00 00 04 47 08 02 00 00 00 7c 8b ab  ...j...G.....|..
     00000020: 78 00 00 00 01 73 52 47 42 00 ae ce 1c e9 00 00  x....sRGB.......
     00000030: 00 04 67 41 4d 41 00 00 b1 8f 0b fc 61 05 00 00  ..gAMA......a...
     00000040: 00 09 70 48 59 73 00 00 16 25 00 00 16 25 01 49  ..pHYs...%...%.I
     00000050: 52 24 f0 aa aa ff a5 ab 44 45 54 78 5e ec bd 3f  R$......DETx^..?
     00000060: 8e 64 cd 71 bd 2d 8b 20 20 80 90 41 83 02 08 d0  .d.q.-.  ..A....
     00000070: f9 ed 40 a0 f3 6e 40 7b 90 23 8f 1e d7 20 8b 3e  ..@..n@{.#... .>
     00000080: b7 c1 0d 70 03 74 b5 03 ae 41 6b f8 be a8 fb dc  ...p.t...Ak.....
     00000090: 3e 7d 2a 22 33 6f de 5b 55 dd 3d 3d f9 20 91 88  >}*"3o.[U.==. ..
    ```
    
    Copiar
    
    ```
     $ pngcheck -v -f mystery.png
     File: fixed.png (202940 bytes)
     chunk IHDR at offset 0x0000c, length 13
         1642 x 1095 image, 24-bit RGB, non-interlaced
     chunk sRGB at offset 0x00025, length 1
         rendering intent = perceptual
     chunk gAMA at offset 0x00032, length 4: 0.45455
     chunk pHYs at offset 0x00042, length 9: 5669x5669 pixels/meter (144 dpi)
     :  invalid chunk length (too large)
     ERRORS DETECTED in fixed.png
    ```
    
9. El `invalid chunk length (too large)`error no especifica un fragmento, por lo que debemos comenzar desde el principio y verificar cada fragmento, conociendo el formato de los fragmentos y la longitud de cada campo: 4 bytes (longitud) - 4 bytes (tipo de fragmento) - longitud en bytes (datos) - 4 bytes (CRC).
    
10. El fragmento que sigue `pHYs`tiene un tamaño de `0xaaaaffa5`, que es muy grande, y un tipo de `\xabDET`que no existe. El tipo de fragmento más cercano es [IDAT](https://www.w3.org/TR/2003/REC-PNG-20031110/#11IDAT) . Corrijamos eso repitiendo el nombre del fragmento con `49 44 41 54`(hexadecimal).
    
11. Para resolver la longitud del fragmento grande, necesitamos calcular la longitud del fragmento y actualizar su valor. `IDAT`Los fragmentos deben ser consecutivos, así que busquemos el siguiente. Encontramos el siguiente IDAT en el desplazamiento `0x10008`. El primer IDAT estaba en el desplazamiento `0x57`. La diferencia es FFB1. Debemos restar 4 bytes por el campo de longitud del segundo IDAT, restar 4 bytes por el CRC del primer IDAT y restar 4 bytes más por el tipo de fragmento del primer IDAT. Restando 12 en total, obtenemos FFA5. Reemplazamos el campo de longitud con `00 00 FF A5`(hexadecimal). El valor original era , `0xAAAAFFA5`así que solo necesitábamos sobrescribir `AAAA`con `0000`.
    
12. La ejecución `pngcheck mystery.png`muestra `mystery.png (1642x1095, 24-bit RGB, non-interlaced, 96.3%).`que no hay errores y podemos abrir la imagen con la bandera:

picoCTF{c0rrupt10n_1847995}

## NOTAS ADICIONALES

## REFERENCIAS