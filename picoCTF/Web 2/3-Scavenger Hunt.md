## RETO
Scavenger Hunt
## DESCRIPCION
There is some interesting information hidden around this site. Can you find it? http://wily-courier.picoctf.net:65080/
## SOLUCION
Se convino el reto de insp3ctor y where are the robots. asi que hice con lo que aprendi de esos retos pude solucionar este.

### 1. La Fuente Original (HTML)
- Abrimos la página del reto: [http://wily-courier.picoctf.net:65080/](http://wily-courier.picoctf.net:65080/)
- Presiona `Ctrl + U` para ver el código fuente.
- Ahí mismo encontramos la primera parte de la flag.
### 2. El Estilo Escondido (CSS)
- En la misma ventana del código fuente, busca el enlace al archivo CSS: `<link rel="stylesheet" type="text/css" href="mycss.css">`.
- Encontramos segunda parte de la flag.
### 3. El Script del Navegador (JS)

- Regresamos al código fuente y buscamos el archivo JavaScript: `<script src="myjs.js"></script>`
- Hice clic en `myjs.js`.
- Da una pista sobre cómo se indexa la página.

- ### 1. La pista del archivo JS
- **Pista:** "¿Cómo evito que Google indexe mi sitio?"
    
- **Respuesta:** Se debe buscar el archivo **`robots.txt`**.
- En el navegador, añadimos `/robots.txt` al final de la URL del reto: `http://wily-courier.picoctf.net:65080/robots.txt`
- Ahí vimos la **Parte 3** de la bandera y una nueva pista(I think this is an apache server... can you Access the next flag?)
### Paso 4: El archivo de configuración de Apache

Añadimos `/.htaccess` al final de la URL en el navegador: `http://wily-courier.picoctf.net:65080/.htaccess`

 Part 4: 3s_2_lO0k
I love making websites on my Mac, I can Store a lot of information there

### Paso 5: El gran final (.DS_Store)

Añadimos `/.DS_Store` al final de la URL en el navegador: `http://wily-courier.picoctf.net:65080/.DS_Store`

y completamos la flag:
picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_9588550}
## NOTAS ADICIONALES
Archivo Robots (`/robots.txt`) Configuración para rastreadores web.
Configuración Apache (`/.htaccess`)Archivos de configuración de servidor.
Metadatos macOS (`/.DS_Store`)Archivos temporales/ocultos del SO.
## REFERENCIAS
https://es.wikipedia.org/wiki/Est%C3%A1ndar_de_exclusi%C3%B3n_de_robots