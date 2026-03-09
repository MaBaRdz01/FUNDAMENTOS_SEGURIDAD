## RETO
SOAP
## DESCRIPCION
The web project was rushed and no security assessment was done. Can you read the /etc/passwd file?[Web Portal](http://saturn.picoctf.net:65477/)
## SOLUCION
1. Se accedió al sitio web proporcionado por el reto y se observó que al presionar el botón **Details** se enviaba una solicitud al servidor.

2. Se utilizó Burp Suite para interceptar la petición HTTP enviada al endpoint `/data`.

3. Se observó que la solicitud utilizaba formato XML:


            <?xml version="1.0" encoding="UTF-8"?>  
            <data>  
            <ID>1</ID>  
            </data>

4. Debido a que el reto sugiere una posible vulnerabilidad XXE, se modificó la solicitud agregando una entidad externa que apunta al archivo `/etc/passwd`.


Payload utilizado:

       <?xml version="1.0" encoding="UTF-8"?>  
       <!DOCTYPE data [  
       <!ENTITY xxe SYSTEM "file:///etc/passwd">  
       ]>  
       <data>  
       <ID>&xxe;</ID>  
       </data>

5. Al enviar la solicitud modificada mediante Burp Suite, el servidor procesó la entidad externa y devolvió el contenido del archivo `/etc/passwd` en la respuesta.

6. Esto confirmó que la aplicación es vulnerable a **XXE**, ya que permite leer archivos internos del sistema.

## NOTAS ADICIONALES
La vulnerabilidad explotada fue **XML External Entity Injection**, que ocurre cuando un servidor procesa XML sin deshabilitar las entidades externas. Esto permite que un atacante acceda a archivos del sistema o incluso realice otras acciones dependiendo de la configuración del servidor.
## REFERENCIAS
