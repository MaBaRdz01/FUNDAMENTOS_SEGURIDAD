## RETO
Redaction gone wrong
## DESCRIPCION
Now you DON’T see me.This [report](https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf) has some critical data in it, some of which have been redacted correctly, while some were not. Can you find an important key that was not redacted properly?
## SOLUCION
Se nos proporciona un archivo PDF llamado `Financial_Report_for_ABC_Labs.pdf`.

Pero vemos que hay palabras que se han ocultado utilizando una especie de “color de fondo” negro. Sin embargo, podemos usar el ratón para selecctionar el texto, y ahí está la _flag_:

`   Financial Report for ABC Labs, Kigali, Rwanda for the year 2021.  Breakdown - Just painted over in MS word.   Cost Benefit Analysis  Credit Debit  This is not the flag, keep looking  Expenses from the  picoCTF{C4n_Y0u_S33_m3_fully}  Redacted document.   `
## NOTAS ADICIONALES

## REFERENCIAS