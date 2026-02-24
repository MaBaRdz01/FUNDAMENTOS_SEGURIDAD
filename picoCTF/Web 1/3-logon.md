## RETO
Logon
## DESCRIPCION
The factory is hiding things from all of its users. Can you login as Joe and find what they've been looking at? http://fickle-tempest.picoctf.net:62054
## SOLUCION
Existen 2 soluciones:
 1. CURL:
 **Uno NO cambiaste la cookie real del navegador**.

Envías una petición HTTP falsa diciendo:
"Soy el administrador"

curl -s http://fickle-tempest.picoctf.net:62054/flag \  
-H "Cookie: username=fany; password=fany; admin=True"

Eso significa:

> “Servidor, aquí te mando una petición manual donde soy admin=True”

💥 El servidor lo cree 
💥 Da la flag  
💥 Pero SOLO para esa petición

2. Cambiar cookie en el navegador:
Dar clic derecho en cualquier parte de la pagina y seleccionar **Inspector** para abrir la herramienta de desarrollo del navegador.

Ir a la seccion de console

Escribir: document.cookie = "admin=True"

ENTER 
![[Pasted image 20260223163817.png]]
## NOTAS ADICIONALES
✔ `curl` → hace request HTTP  
✔ `-H` → agrega headers  
✔ `"Cookie: ..."` → simula cookies  
✔ `admin=True` → truco principal 😈

## REFERENCIAS
