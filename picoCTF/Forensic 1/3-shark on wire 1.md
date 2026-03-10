## RETO
shark on wire 1
## DESCRIPCION
We found this [packet capture](https://challenge-files.picoctf.net/c_fickle_tempest/134d2a2cf6ec5b7e757effc9b32977af7cc324b8e99a5ddb64737794a14dc18d/capture.pcap). Recover the flag.
## SOLUCION
1. **Abrir el archivo** `capture.pcap` con Wireshark.
    
2. **Filtra por UDP:** Escribir `udp` en la barra de filtros superior y presiona Enter.
    
3. **Sigue los flujos (Follow Stream):**
    
    - Hacer clic derecho sobre cualquier paquete UDP.
        
    - Selecciona **Follow** -> **UDP Stream**.
        
4. **Navega por los flujos:** Aparecerá una ventana con texto. En la esquina inferior derecha verás un número de "Stream" (0, 1, 2...). Ir cambiando las flechitas para pasar al siguiente flujo hasta que veas algo que empiece con `picoCTF{...}`.
       ==picoCTF{StaT31355_636f6e6e}==
## NOTAS ADICIONALES
A diferencia de TCP, el protocolo **UDP (User Datagram Protocol)** no requiere un saludo inicial, lo que lo hace común para transmisiones rápidas. En este reto, la bandera fue enviada fraccionada o íntegra dentro del cuerpo de datos de varios paquetes UDP.

Se utilizó la función **Follow UDP Stream** de Wireshark para reconstruir la conversación lógica entre dos nodos. Esta técnica permite leer los datos intercambiados como una sola cadena de texto, ignorando las cabeceras de red que separarían los paquetes individualmente.

Durante el análisis, se descartaron paquetes de protocolos como DNS o ARP, ya que su función es de control de red y rara vez contienen _payloads_ de aplicaciones personalizadas en este nivel de retos.
## REFERENCIAS