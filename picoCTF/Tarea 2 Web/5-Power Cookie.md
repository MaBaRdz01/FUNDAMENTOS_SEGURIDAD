## RETO
Power Cookie
## DESCRIPCION
## SOLUCION
1. **Entra al sitio:** 
    
2. **Haz clic en el botón:** Te llevará a una página que dice que no tienes permisos de administrador.
    
3. **Abrir las Herramientas de Desarrollador:**
    
    - Presiona `F12` o `Ctrl + Shift + I` en tu navegador.
        
    - Ir a la pestaña **Storage**.
        
4. **Localiza las Cookies:** * En el menú de la izquierda, busca la sección **Cookies** y selecciona la URL del reto.
    
5. **Modifica el valor:**
    
    - Se vera una cookie llamada`isAdmin`.
        
    - Su valor actual es`0` (que significa "falso" o no es admin).
        
    - Hacer doble clic en el `0` y cámbialo a `1`.
        

 6. Obtén la Flag

Una vez que se haya cambiado el valor de la cookie a `1`:

1. **Refresca la página**.
    
2. El servidor leerá la cookie modificada, pensará que somos el administrador y nos mostrará la flag:
     **picoCTF{gr4d3_A_c00k13_0d351e23}**
## NOTAS ADICIONALES
Este es un ejemplo de una vulnerabilidad de **Control de Acceso Quebrado**. El servidor nunca debería confiar en un valor que el usuario puede editar fácilmente en su propio navegador. La lógica de "quién es administrador" debería manejarse siempre de forma segura en el servidor

## REFERENCIAS