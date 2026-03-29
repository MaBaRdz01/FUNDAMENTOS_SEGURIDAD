## RETO
head-dump
## DESCRIPCION
Welcome to the challenge! In this challenge, you will explore a web application and find an endpoint that exposes a file containing a hidden flag.The application is a simple blog website where you can read articles about various topics, including an article about API Documentation. Your goal is to explore the application and find the endpoint that generates files holding the server’s memory, where a secret flag is hidden.The website is running [picoCTF News](http://verbal-sleep.picoctf.net:53810/).

## SOLUCION
**Paso 1: Explorando la aplicación web**

El desafío comienza con un sencillo sitio web de blog. Tras iniciar la instancia, navegué por las páginas, prestando mucha atención a los enlaces y los puntos finales ocultos. Un artículo titulado « [_Documentación de la API»_](http://verbal-sleep.picoctf.net:59989/api-docs) me llamó la atención. Al hacer clic en él, me redirigió a **/api-docs,** donde se encontraba Swagger UI, una herramienta para visualizar e interactuar con las API.

**Paso 2: Identificación del punto final crítico**
Swagger reveló varias rutas de API, pero el endpoint **/heapdump en la sección** _de Diagnóstico_ me llamó la atención. La descripción sugería la generación de un volcado de memoria, lo que coincidía con el nombre del desafío.

**Paso 3: Ejecutar el punto final**

Utilizando la función "Pruébalo" de Swagger, activé el punto final **/heapdump** . Esta acción descargó un archivo **.heapsnapshot** que contenía los datos de memoria del servidor.

**Paso 4: Extracción de la bandera**
ABRI EL DOCUMENTO Y BUSQUE LA PALABRA PICO :
picoCTF{Pat!3nt_15_Th3_K3y_8df117c1}


## NOTAS ADICIONALES
El desafío _de volcado de memoria_ reforzó la importancia de la paciencia y la exploración metódica en ciberseguridad. Al combinar el análisis de API con un análisis de datos eficiente, descubrimos la vulnerabilidad en minutos, demostrando que, a veces, la clave del éxito reside en saber dónde buscar.
## REFERENCIAS