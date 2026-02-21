## RETO
Serpentine
## DESCRIPCION
Find the flag in the Python script
![Download Python script](https://artifacts.picoctf.net/c/36/serpentine.py)
## SOLUCION
SEGUI LOS CONSEJOS O BIEN PISTAS QUE DABAN Y PUES AL ABRIR CON EL EDITOR nano LIT NOS ENCONTRAMOS QUE DA LA CONTRASEÑA:

flag = str_xor(flag_enc, '**enkidu**')

Y solo hay que ponerla en donde deberia de ir correctamente en el codigo de python que te dan, ósea en la opcion b :
elif choice == 'b':
      ###print('\nOops! I must have misplaced the print_flag function! Check my source code!\n\n')
      print(**print_flag()**)

despues de corregir el codigo:
┌──(kali㉿kali)-[~/Downloads]
└─$ ==python3 serpentine.py==
/home/kali/Downloads/serpentine.py:41: SyntaxWarning: invalid escape sequence '\ '
  /     \      .- ~ ~ -.

    Y
  .-^-.
 /     \      .- ~ ~ -.
()     ()    /   _ _   `.                     _ _ _
 \_   _/    /  /     \   \                . ~  _ _  ~ .
   | |     /  /       \   \             .' .~       ~-. `.
   | |    /  /         )   )           /  /             `.`.
   \ \_ _/  /         /   /           /  /                `'
    \_ _ _.'         /   /           (  (
                    /   /             \  \
                   /   /               \  \
                  /   /                 )  )
                 (   (                 /  /
                  `.  `.             .'  /
                    `.   ~ - - - - ~   .'
                       ~ . _ _ _ _ . ~
elcome to the serpentine encourager!


a) Print encouragement
b) Print flag
c) Quit

What would you like to do? (a/b/c) b
**picoCTF{7h3_r04d_l355_7r4v3l3d_aa2340b2}**

## NOTAS ADICIONALES
A veces los códigos traen la propia contraseña que pueda dar acceso agente maliciosa. 

## REFERENCIAS
