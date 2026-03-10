## RETO
IntroToBurp
## DESCRIPCION
Additional details will be available after launching your challenge instance.
## SOLUCION
1. Acceder a la URL proporcionada en el navegador y se abrirá una **página de registro**.
2. Ingresamos el valor requerido y hacemos clic en el botón **Registrar** . La aplicación solicitará una **contraseña de un solo uso (OTP)** en la página siguiente.
3. Proporcionar cualquier valor aleatorio como **OTP** y hacer clic en **Enviar,** lo que mostrará un mensaje como " **OTP no válido** ".
4. Hacer clic en el botón Atrás para abrir de nuevo la página **de autenticación de 2FA** . Ahora proporcionar cualquier valor y capturar la solicitud con la herramienta burp suite, ya que el nombre del desafío es " **IntroToBurp** " y necesitamos resolverlo usando la herramienta burp.
5. Enviar la solicitud capturada a Burp Repeater para que podamos probar diferentes tipos de entradas de usuario, como inyección SQL y cargas útiles XSS, caracteres en lugar de números o el envío de un valor en blanco. En todos estos casos, la aplicación generará la misma respuesta con el mensaje de error " **OTP no válido** ".
6. Como esta solicitud tiene el método **POST** y, en general, se espera un cuerpo en la solicitud POST, podemos intentar generar una respuesta eliminando **otp=0000** del cuerpo de la solicitud por completo.
7. Se observará que la aplicación ha revelado el valor **de la bandera** para el cuerpo de la solicitud vacío.
![[Pasted image 20260309084014.png]]



## NOTAS ADICIONALES
El uso de herramientas como Burp Suite es fundamental en auditorías web para probar cómo reacciona un servidor ante datos inesperados o malformados.
## REFERENCIAS