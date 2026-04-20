## RETO
 rsa-pop-quiz
## DESCRIPCION
Class, take your seats! It's PRIME-time for a quiz...nc fickle-tempest.picoctf.net 51541
## SOLUCION
Para resolver este reto, se aplicaron las fórmulas fundamentales del sistema criptográfico RSA en múltiples etapas:

1. **Cálculo de $n$:** Dado $p$ y $q$, se utilizó la fórmula $n = p \times q$.
    
2. **Factorización de $n$:** Dado $n$ y $p$, se encontró $q$ mediante la división $q = n / p$.
    
3. **Análisis de Factibilidad:** Se identificaron problemas donde $n$ era un número excesivamente grande sin factores conocidos. En estos casos, se respondió que **no era factible (N)** debido a la dificultad computacional de factorizar números primos de gran magnitud.
    
4. **Cálculo del Totient:** Se utilizó la función de Euler: $\phi(n) = (p-1)(q-1)$.
    
5. **Cifrado/Descifrado:** * Para cifrar: $c = m^e \pmod{n}$.
    
    - Para descifrar: Primero se calculó la clave privada $d$ como el inverso multiplicativo modular de $e \pmod{\phi(n)}$, y luego se aplicó $m = c^d \pmod{n}$.
        

### Obtención de la Flag

En el último problema, tras obtener el **plaintext** final:

`218378661235194013475375491560393839271890611748313869466505982183260263630681999229565`

Se procedió a convertir este valor decimal a hexadecimal y posteriormente a ASCII utilizando Python:


>>> # Convertir a hexadecimal, quitar el '0x' y convertir a ASCII
>>> flag = bytes.fromhex(hex(n)[2:]).decode('ascii')
>>> print(flag)
picoCTF{wA8_th4till3aGal..ob6435DeB}
>>>


## NOTAS ADICIONALES
- **Manejo de Precisión:** Debido a la magnitud de los números involucrados, fue indispensable utilizar el tipo de dato `int` de Python, que permite precisión arbitraria, evitando errores de desbordamiento comunes en otros lenguajes.
    
- **Eficiencia:** Para las operaciones de exponenciación modular, se utilizó la función nativa `pow(base, exp, mod)`, la cual implementa el algoritmo de "exponenciación binaria" para obtener resultados en milisegundos.
    
- **Formato de Salida:** Un error crítico durante el reto fue el envío de números con espacios o saltos de línea; el servidor de PicoCTF es estricto y solo acepta una cadena continua de dígitos decimales.
## REFERENCIAS
https://medium.com/@sobatistacyber/picoctf-writeup-rsa-pop-quiz-b13fbf4c6d2c