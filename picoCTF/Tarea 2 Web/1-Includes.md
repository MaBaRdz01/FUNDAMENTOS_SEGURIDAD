## RETO
Includes
## DESCRIPCION
Can you get the flag?Go to this [website](http://saturn.picoctf.net:58679/) and see what you can discover.
## SOLUCION
#### 1. Inspeccionar el Código Fuente

Una vez que abierto el URL del reto:

1. Hacer derecho en cualquier parte de la página y selecciona **"Ver código fuente de la página"** (o presiona `Ctrl + U`).
    
2. Buscar las etiquetas que llaman a archivos externos.
    
    - `<link rel="stylesheet" type="text/css" href="style.css">`
        
    - `<script src="script.js"></script>`
        

#### 2. Revisar el archivo CSS (`style.css`)

Hacer clic en el enlace de `style.css` para abrirlo.

- Busca una línea que empiece con `/*` y termine con `*/`.
    
- Es muy probable que se encuentre la **primera mitad** de la bandera aquí. 
     ==picoCTF{1nclu51v17y_1of2_==

#### 3. Revisar el archivo JavaScript (`script.js`)

Ahora regresa y haz clic en el enlace de `script.js`.

- Busca comentarios que empiecen con `//`.
    
- Aquí debería estar la **segunda mitad** de la bandera. 
      ==f7w_2of2_6edef411}==

y al final se unen las dos partes para armar la bandera:
 ==picoCTF{1nclu51v17y_1of2_f7w_2of2_6edef411}==

## NOTAS ADICIONALES
Las tareas anteriores se pueden parecer a los nuevos retos.

## REFERENCIAS