## RETO
Roboto Sans
## DESCRIPCION
The flag is somewhere on this web application not necessarily on the website. Find it.

Additional details will be available after launching your challenge instance
## SOLUCION
1. **Accede al archivo robots.txt:** Ir a la URL del reto y, en la barra de direcciones del navegador, agregar `/robots.txt` al final.
        
2. **Analiza el contenido:** Se ve un texto plano.  Busca una que parezca una **cadena de texto en Base64** (letras y números que parecen aleatorios). 
        `anMvbXlmaWxlLnR4dA==`
    
3. **Decodifica la ruta:** Esa cadena es en realidad una ruta de carpeta o archivo "oculta" que ha sido codificada. Puedes usarse una herramienta como [CyberChef](https://gchq.github.io/CyberChef/) o simplemente buscar "Base64 decoder" en Google.
    
    - Copia la cadena de `robots.txt`.
        
    - Decodifícala y se obtendra algo como `js/myfile.txt` o una ruta similar, dependiendo.
        
4. **Navega a la ubicación secreta:** Copia esa ruta decodificada y pégala al final de la URL principal del reto.
    
    - Ejemplo: `http://saturn.picoctf.net:58819/js/myfile.txt`
        

 5. Captura la Flag

Al cargar esa página u archivo oculto, aparecerá la flag: 

`picoCTF{Who_D03sN7_L1k5_90B0T5_718c9043}`

## NOTAS ADICIONALES
Este reto demuestra que **`robots.txt` no es un mecanismo de seguridad**. Solo es una sugerencia para los buscadores. Si pones una ruta secreta ahí, un atacante la encontrará en segundos simplemente leyendo el archivo.

## REFERENCIAS
https://emn178.github.io/online-tools/base64_decode.html