## RETO
Python Wrangling
## DESCRIPCION
Python scripts are invoked kind of like programs in the Terminal...Can you run [ende.py](https://challenge-files.picoctf.net/c_wily_courier/1b9b921ec0fd3ea71d7e326c84ff94912e8e7d2d67c277af04005cace61cf230/ende.py) using [password.txt](https://challenge-files.picoctf.net/c_wily_courier/1b9b921ec0fd3ea71d7e326c84ff94912e8e7d2d67c277af04005cace61cf230/password.txt) to get [flag.txt.en](https://challenge-files.picoctf.net/c_wily_courier/1b9b921ec0fd3ea71d7e326c84ff94912e8e7d2d67c277af04005cace61cf230/flag.txt.en)?
## SOLUCION
1. Descargar los archivos y tenerlos en la misma carpeta
2. Ejecutar el comando :                     python3 ende.py -d flag.txt.en
3. Cuando ejecutes el comando anterior, el script te pedirá una **"Password"**.

4. Abre el archivo `password.txt`

5. Copia la cadena de texto que aparece.

6. Pégala en la terminal cuando el script te la pida y presiona **Enter**.

┌──(kali㉿kali)-[~/Downloads/reto8]
└─$ python3 ende.py -d flag.txt.en
Please enter the password:720b6ad346f84cd483c60c7464dd95d4
picoCTF{4p0110_1n_7h3_h0us3_9c5f9bcf}

## NOTAS ADICIONALES
El reto 'Python Wrangling' demuestra el uso de argumentos posicionales y banderas (`flags`) en la ejecución de scripts. Se utilizó el intérprete de **Python 3** para invocar el módulo `ende.py` con el argumento `-d` (decryption), dirigiendo la operación hacia el archivo cifrado `flag.txt.en`.

**Seguridad y Flujo de Datos:** El script implementa una capa de autenticación simple mediante una contraseña almacenada en un archivo de texto plano (`password.txt`). Este ejercicio resalta la importancia de la gestión de entradas de usuario y la automatización de tareas criptográficas mediante lenguajes de alto nivel.
## REFERENCIAS