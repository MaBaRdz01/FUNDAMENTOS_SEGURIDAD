## RETO
Cookies
## DESCRIPCION

## SOLUCION
  Usando Burp Suite (El camino más didáctico)
1. Activa **FoxyProxy** (perfil Burp).
2. En Burp Suite, asegúrate de que **Intercept is ON** (en la pestaña Proxy).
3. Refresca la página del reto en el navegador.
4. Cuando Burp capture la petición, busca en el texto una línea que diga: `Cookie: name=0` (o `name=-1`).
5. Haz clic derecho y selecciona **Send to Repeater**.
6. Ve a la pestaña **Repeater** y haz clic en **Send**. Verás la respuesta a la derecha.

En lugar de probar números uno por uno manualmente, puedes automatizarlo:

7. En la petición del **Repeater**, haz clic derecho y selecciona **Send to Intruder**.
8. En **Intruder** -> **Positions**, selecciona solo el número después de `name=` y haz clic en **Add §**. Debería verse así: `name=§0§`.
9. En la pestaña **Payloads**:
- **Payload type:** Numbers.
- **From:** 1
- **To:** 50 (por ejemplo).
-  **Step:** 1
7. Haz clic en **Start Attack**.
8. Revisa los resultados. Busca el que tenga una **Length** (longitud) diferente a los demás


## NOTAS ADICIONALES
Fue necesario activar el seguimiento de redirecciones (**Follow Redirections**) en los ajustes del Intruder para ver el contenido real de la página `/check`.

Si todos los resultados tienen un tamaño de **394**, significa que el servidor te está devolviendo la misma página de "Error/Redirección" para todos los intentos. Esto sucede porque el Intruder está atacando la URL de `/check` sin procesar la redirección correctamente.

Para solucionarlo y encontrar la flag de **Cookies**, seguí estos pasos:

### 1. El problema del "302 Found"

En tu captura de Burp, la respuesta es un código **302 Found**. Esto significa que el servidor dice: "Ve a buscar la galleta a otra página". Si el Intruder solo ve esa respuesta corta de redirección, el tamaño (Length) siempre será el mismo (394 bytes) porque no está entrando a ver el contenido de la galleta.

### 2. Cómo arreglarlo en el Intruder

Para que el Intruder te muestre el contenido real de la página (y así varíe el `Length`), haz esto:

1. En la ventana de **Intruder**, ve a la pestaña **Settings** (o **Options** en versiones anteriores).
2. Busca la sección llamada **Redirections**.
3. Cambia la configuración a **Always** y marca la casilla **Process cookies in redirections**.
4. Vuelve a la pestaña **Payloads** y dale a **Start Attack** otra vez.
## REFERENCIAS