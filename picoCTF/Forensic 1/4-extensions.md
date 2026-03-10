## RETO
## DESCRIPCION
## SOLUCION
1. ** **Usar el comando `file`:**  Este comando ignora la extensión y analiza el contenido real.           `file flag.txt`
    _Resultado esperado:_ ¡Sorpresa! No es un texto, es una imagen **PNG**.
- **Cambia la extensión:** Renombrar el archivo:
       `mv flag.txt flag.png`
- **Abrir la imagen:** Usa cualquier visor de imágenes o simplemente arrastra el archivo `flag.png` a tu navegador. La bandera estará escrita dentro de la imagen.**

`picoCTF{now_you_know_about_extensions}`
## NOTAS ADICIONALES
El análisis con la utilidad `file` reveló que los primeros bytes del archivo corresponden al estándar de **PNG** (`89 50 4E 47`). Esto demuestra que el sistema operativo utiliza estos encabezados para determinar la naturaleza del archivo, independientemente del nombre asignado por el usuario.

## REFERENCIAS