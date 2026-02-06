## RETO: 
Bases
## DESCRIPCION:
What does this bDNhcm5fdGgzX3IwcDM1 mean? I think it has something to do with bases.
## SOLUCION:
### SOLUCION 1 - USANDO CYBERCHEF
https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=YkROaGNtNWZkR2d6WDNJd2NETTE
respuesta: l3arn_th3_r0p35
### SOLUCION 2-USANDO PYTHON
>>> `import base64`
`...`
`... s = "bDNhcm5fdGgzX3IwcDM1"`
`... decoded = base64.b64decode(s).decode("utf-8")`
`... print(decoded)`
`...`
`l3arn_th3_r0p35`
>>>

### SOLUCION 3-Linux
`┌──(kali㉿kali)-[~]`
`└─$ echo "bDNhcm5fdGgzX3IwcDM1" | base64 -d` 
`l3arn_th3_r0p35`                                                              
## NOTAS ADICIONALES
CYBERCHEF: PERMITE CONVERTIR DE HEXADECIMAL A CODIGO ASCII

PYTHON: NOS AYUDA A RESOLVER LOS PROBLEMAS MAS EFICIENTE 
## REFERENCIAS
https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=YkROaGNtNWZkR2d6WDNJd2NETTE

python

linux