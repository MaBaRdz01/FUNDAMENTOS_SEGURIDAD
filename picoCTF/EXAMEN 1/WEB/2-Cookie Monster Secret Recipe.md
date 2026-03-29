## RETO
Cookie Monster Secret Recipe
## DESCRIPCION
Cookie Monster has hidden his top-secret cookie recipe somewhere on his website. As an aspiring cookie detective, your mission is to uncover this delectable secret. Can you outsmart Cookie Monster and find the hidden recipe?You can access the Cookie Monster [here](http://verbal-sleep.picoctf.net:52749/) and good luck
## SOLUCION
1. Haz clic en el enlace que aparece en el portal para acceder al desafío. Se abrirá una página **de inicio de sesión**
2. Introduce cualquier término aleatorio, por ejemplo, " **prueba"** : **prueba,** como credenciales y haz clic en el botón **"Iniciar sesión"** . Aparecerá un mensaje **de "Acceso denegado"** con la siguiente sugerencia **_: "¿Has comprobado tus cookies últimamente?_** ".  
Siguiendo esta sugerencia, abre la pestaña **"Cookies** " del navegador y observa que se ha generado una cookie llamada " **_secret_recipe_** " incluso después de haber intentado iniciar sesión sin éxito.

 3. Copia el valor de la cookie y pégalo en el **Burp Decoder** .  
Usa **_Decodificar como URL > Decodificar como Base64_** para obtener el valor **de la bandera** .
picoCTF{c00k1e_m0nster_l0ves_c00kies_4736F6CB}

## NOTAS ADICIONALES
 Verifique siempre los valores almacenados en las cookies, especialmente si la aplicación maneja datos confidenciales.
## REFERENCIAS
https://www.base64decode.org/es/