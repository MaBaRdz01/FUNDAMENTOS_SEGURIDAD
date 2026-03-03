## RETO
Irish-Name-Repo 1
## DESCRIPCION
Do you think you can log us in? Try to see if you can login! http://fickle-tempest.picoctf.net:54342.
## SOLUCION
### Pasos finales:

1. Ve a la página del reto.

2. Haz clic en el menú (las tres líneas) y selecciona **Admin Login**.

3. En el campo de usuario escribe: `admin' OR '1'='1' --`

4. Pulsa **Login**.

5. picoCTF{s0m3_SQL_85832275}

## NOTAS ADICIONALES
 1. El Análisis

El sitio web tiene un formulario de "Admin Login". Cuando introdujo un usuario y contraseña, la base de datos ejecuta una consulta similar a esta:

`SELECT * FROM users WHERE username = '$username' AND password = '$password';`

Si se logra manipular la consulta para que siempre sea **verdadera**, el sistema nos dejará entrar sin saber la contraseña real.

 2. La Solución 

Para engañar a la base de datos, se debe de introducir lo siguiente en el campo de **Username**:

- **Payload:** `admin' OR '1'='1' --`

- **Contraseña:** Dejarla en blanco o bien poner cualquier cosa.

3. ¿Por qué funciona?

Al introducir ese código, la consulta interna se transforma en algo como esto:

`SELECT * FROM users WHERE username = 'admin' OR '1'='1' --' AND password = '...';`

- **`'1'='1'`**: Es una condición que siempre es cierta (True).

- **`OR`**: Hace que toda la sentencia sea verdadera si al menos una parte lo es.

- **`--`**: Es el símbolo de comentario en SQL. Esto hace que el resto de la consulta (la verificación de la contraseña) sea ignorada por el servidor.

## REFERENCIAS

