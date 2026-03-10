## RETO
Local Authority
## DESCRIPCION
Can you get the flag?

Additional details will be available after launching your challenge instance.
## SOLUCION
1. Hacer clic derecho en la página de error y selecciona **"Ver código fuente de la página"** (o presiona `Ctrl + U`).
    
2. Busca etiquetas `<script>` o archivos `.js` externos.
3. 
4. Haz clic en el enlace de ese archivo para ver su contenido.

5. Dentro de ese archivo JavaScript, se encontrara una función que compara lo que escribiste con las credenciales "correctas". 

JavaScript

        function checkPassword(username,                   password)
        {
            if( username === 'admin' &&                password ===   'strongPassword098765' )
             {
                return true;
             }
              else
            {
                return false;
            }
        }


6. Copiar el **usuario** y la **contraseña** que se encontro en el código JavaScript.
    
7. Regresa a la página principal del reto.
    
8. Ingresa esas credenciales.
    
9. Una vez que entremos, la página mostrará la flag:

       picoCTF{j5_15_7r4n5p4r3n7_05df90c8}
## NOTAS ADICIONALES
Este reto enseña que **nunca se debe confiar en la validación del lado del cliente**. Si la contraseña está en el JavaScript, cualquier usuario puede verla simplemente leyendo el código que su propio navegador descargó.

## REFERENCIAS