## RETO
SansAlpha
## DESCRIPCION
The Multiverse is within your grasp! Unfortunately, the server that contains the secrets of the multiverse is in a universe where keyboards only have numbers and (most) symbols. `ssh -p 61541 ctf-player@mimas.picoctf.net` Use password: `83dcefb7`
## SOLUCION
SansAlpha$ ${_1:10:1}
SansAlpha$ /???/b??64
SansAlpha: Unknown character detected
SansAlpha$ ??????/*
bash: blargh/flag.txt: Permission denied

SansAlpha$ _1=`$ 2>&1`
SansAlpha$ ./*/*
bash: ./blargh/flag.txt: Permission denied

SansAlpha$ /???/?${_1:9:1}?${_1:10:1}


SansAlpha$ /???/?${_1:9:1}?${_1:10:1} "$(<./*/????.???)"
return 0 picoCTF{7h15_mu171v3r53_15_m4dn355_36a674c0}

## NOTAS ADICIONALES
Se exploró el uso de `${_:1:1}` para intentar recuperar caracteres alfabéticos de las variables internas del Shell (`$_`). Esta técnica permite construir comandos dinámicamente en entornos donde el teclado está filtrado. Sin embargo, para maximizar la eficiencia en la exfiltración, se optó por la invocación directa del binario `base64` mediante máscaras de posición en el subdirectorio `blargh`, logrando el bypass de la restricción alfabética de manera exitosa.
## REFERENCIAS