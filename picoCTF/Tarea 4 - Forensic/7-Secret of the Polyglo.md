## RETO
Secret of the Polyglo
## DESCRIPCION
The Network Operations Center (NOC) of your local institution picked up a suspicious file, they're getting conflicting information on what type of file it is. They've brought you in as an external expert to examine the file. Can you extract all the information from this strange file?Download the suspicious file [here](https://artifacts.picoctf.net/c_titan/97/flag2of2-final.pdf).
## SOLUCION
PS C:\Users\maria\Downloads> strings.exe .\flag2of2-final.pdf | Select-String "picoCTF"
C:\Users\maria\Downloads> Copy-Item .\flag2of2-final.pdf .\parte1.png

PS C:\Users\maria\Downloads> Start-Process .\parte1.png
PS C:\Users\maria\Downloads> Start-Process .\flag2of2-final.pdf
## NOTAS ADICIONALES

## REFERENCIAS