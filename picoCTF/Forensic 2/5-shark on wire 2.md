## RETO
shark on wire 2
## DESCRIPCION
Encontramos esta [captura de paquete](https://challenge-files.picoctf.net/c_fickle_tempest/d2051a169bcab758191e43355c6954ae40a96b0791d75ad33737c7e9ca42703b/capture.pcap) . Recupera la bandera.
## SOLUCION
Utilice la función de búsqueda de Wireshark para buscar la bandera o las pistas.

Tras analizar todos los bytes de los paquetes que contienen la cadena 'pico', observé que todos y cada uno de ellos corresponden al protocolo UDP. Por lo tanto, utilicé un filtro para mostrar únicamente los paquetes que utilizan dicho protocolo.

Mientras revisaba el registro, noté un byte de paquete que tenía la cadena 'start'.

El seguimiento del flujo UDP no arrojó ningún resultado, así que intenté ver todos los paquetes con la misma dirección IP como origen.

Pero después de hacer esto, todos los bytes del paquete debajo del que contiene la cadena 'start' solo contienen la cadena 'aaaaa'.

De todas las cadenas de bytes del paquete (excluyendo la que contiene la cadena 'start'), no parece haber ninguna diferencia entre una y otra. Pero noté que el valor hexadecimal cambia en cada byte del paquete.

Tras examinar los detalles del paquete, observo que cada puerto tiene un puerto de origen diferente. Lo único que tienen en común es que todos los puertos son superiores a 5000.

Para continuar con esta pista, uso 'tshark' y redirijo la salida a 'grep' para tomar el puerto de origen y escribir la salida en un archivo.

> tshark -r capture.pcap -Y “ip.src == 10.0.0.66” -V | grep -i “source port” > resultado

Y cuando leí el archivo 'result' con este comando "cat result | cut -d ":" -f 2" obtuve este resultado:

> 5000  
> 5112  
> 5105  
> 5099  
> 5111  
> 5067  
> 5084  
> 5070  
> 5123  
> 5112  
> 5049  
> 5076  
> 5076  
> 5102  
> 5051  
> 5114  
> 5051  
> 5100  
> 5095  
> 5100  
> 5097  
> 5116  
> 5097  
> 5095  
> 5118  
> 5049  
> 5097  
> 5095  
> 5115  
> 5116  
> 5051  
> 5103  
> 5048  
> 5125

Luego creé un script de Python para editar fácilmente todos esos números.

> contenido = “””5112  
> 5105  
> 5099  
> 5111  
> 5067  
> 5084  
> 5070  
> 5123  
> 5112  
> 5049  
> 5076  
> 5076  
> 5102  
> 5051  
> 5114  
> 5051  
> 5100  
> 5095  
> 5100  
> 5097  
> 5116  
> 5097  
> 5095  
> 5118  
> 5049 5097  
> 5095  
> 5115  
> 5116  
> 5051  
> 5103  
> 5048  
> 5125  
> "””
> 
> contenido = contenido.split()

Convertí la cadena en un array, de esa forma puedo modificar cada índice fácilmente. Ahora la variable 'content' contiene un array con los puertos de origen. Como cada puerto sigue siendo una cadena, convierto cada valor del array 'content' en un número entero.

> dígito = []
> 
> para i en contenido:  
> dígito.append(int(i))

Ahora, digit contiene el origen de cada puerto como un número entero.

Después de revisar el puerto de origen, noto que si resto 5000 por cada puerto de origen, obtendré un valor ASCII.

> resultado = “”
> 
> para i en dígito:  
> y = i - 5000  
> resultado += chr(y)

Y si imprimo el resultado obtengo esta bandera:

> picoCTF{p1LLf3r3d_data_v1a_st3g0}
## NOTAS ADICIONALES

## REFERENCIAS