## RETO
- plumbing
## DESCRIPCION
Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag?

Additional details will be available after launching your challenge instance.
## SOLUCION
si pongo:
nc fickle-tempest.picoctf.net 63919
suelta mucha informacion y no se detiene y no podria ver la bandera.
entonces se usa el | grep picoCTF:

nc fickle-tempest.picoctf.net 63919 | grep picoCTF

y da la bandera que en este caso es :
picoCTF{digital_plumb3r_d3246b6B}

`┌──(kali㉿kali)-[~]`
`└─$ nc fickle-tempest.picoctf.net 63919 | grep picoCTF`
`picoCTF{digital_plumb3r_d3246b6B}`

## NOTAS ADICIONALES

- `nc ...` → se conecta al servidor
    
- `|` → manda la salida al siguiente comando
    
- `grep picoCTF` → busca SOLO líneas que tengan `picoCTF`


## REFERENCIAS
Linux
