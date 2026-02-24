## RETO
Based
## DESCRIPCION
To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337?

Additional details will be available after launching your challenge instance.
## SOLUCION
MarianaRodriguez-picoctf@webshell:~$ nc fickle-tempest.picoctf.net 51414
Let us see how data is stored
==animation==
Please give the 01100001 01101110 01101001 01101101 01100001 01110100 01101001 01101111 01101110 as a word.
...
you have 45 seconds.....

Input:
animation

La primera nos dio el resultado solo que estaba escondido en el enunciado 

Luego te da para convertir en octal y hexadecimal que son convertidos con ayuda de cyberchef

## NOTAS ADICIONALES
Había la forma de hacerlo con el lenguaje de Python pero era el procedimiento mas tardado. 

## REFERENCIAS
octal:
https://toolbox.itsec.tamu.edu/#recipe=From_Binary('Space',8/disabled)From_Octal('Space')&input=MTU2IDE2NSAxNjIgMTYzIDE0NQ

Hexadecimal:
https://toolbox.itsec.tamu.edu/#recipe=From_Hex('Auto')&input=NmM2MTZkNzA