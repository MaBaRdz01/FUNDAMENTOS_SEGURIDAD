## RETO
m00nwalk
## DESCRIPCION
Decodifica este [mensaje](https://challenge-files.picoctf.net/c_fickle_tempest/f75cb0bb148301a92ee34a572e39d931d62c9c225f69e4b801ffa0fb6d2fe17b/message.wav) de la luna.
## SOLUCION
1. Instalar `qsstv`con`apt-get install qsstv`
    
2. Correr`pactl load-module module-null-sink sink_name=virtual-cable`
    
3. Ejecuta `pavucontrol`. Aparecerá una interfaz gráfica de usuario (GUI). Ve a la pestaña "Dispositivos de salida" para verificar que tienes el dispositivo "Salida nula".
    
4. Ejecuta `qsstv`el programa. Aparecerá la interfaz gráfica de usuario (GUI). Ve a "Opciones" -> "Configuración" -> "Sonido" y selecciona la interfaz de audio "PulseAudio".
    
5. De vuelta en la `pavucontrol`interfaz gráfica de usuario, seleccione la pestaña "Grabación" y especifique que QSSTV debe capturar el audio de la salida nula.
    
6. La pista preguntaba "¿Cuál es la mascota de CMU?" - la respuesta es "Scotty, el perro Scottie". Esto sugiere que debemos seleccionar "Scottie 1" como "Modo" de QSSTV. Seleccione también "Inclinación automática".
    
7. Ejecutar `paplay -d virtual-cable message.wav`para crear la imagen.
    
8. Desconecta el cable de audio virtual para que el audio se reproduzca con normalidad:
    
    Copiar
    $ pactl list short modules | grep null
    25      module-null-sink        sink_name=virtual-cable
    $ pactl unload-module 25

Bandera:

`picoCTF{beep_boop_im_in_space}`

## NOTAS ADICIONALES

## REFERENCIAS