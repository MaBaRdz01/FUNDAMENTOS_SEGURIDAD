## RETO
asm2
## DESCRIPCION
What does asm2(0xf,0x17) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://challenge-files.picoctf.net/c_fickle_tempest/111d025d4750385ea525035ae7b10ebb3c4518f39726f774aa34c8523e52329e/test.S)
## SOLUCION
Parámetros iniciales

La función recibe dos valores: `asm2(0xf, 0x17)`.

- `[ebp+0x8]` (Arg1) = **0xf** (15 en decimal)
    
- `[ebp+0xc]` (Arg2) = **0x17** (23 en decimal)
    

Análisis del Código (Paso a paso)

1. **Configuración de variables locales:**
    
    - `<+10>` a `<+13>`: Toma el Arg2 (**0x17**) y lo guarda en `[ebp-0x4]`.
        
    - `<+16>` a `<+19>`: Toma el Arg1 (**0xf**) y lo guarda en `[ebp-0x8]`.
        
    - **Estado inicial:** `var1 = 0x17`, `var2 = 0xf`.
        
2. **El Salto al Bucle:**
    
    - `<+22>` salta directamente a `<+35>` para hacer la primera comparación.
        
3. **La Condición (`<+35>` y `<+42>`):**
    
    - Compara `var2` (`[ebp-0x8]`) con **0xd72d**.
        
    - `jle`: Si `var2` es **menor o igual** a $0xd72d$, vuelve a subir a `<+24>`.
        
4. **El Cuerpo del Bucle (`<+24>` a `<+28>`):**
    
    - `add [ebp-0x4], 0x1`: A `var1` le suma **1**.
        
    - `add [ebp-0x8], 0xcb`: A `var2` le suma **0xcb** (203 en decimal).
        

---

El Cálculo (La parte lógica)

El bucle se repetirá hasta que `var2` supere **0xd72d**.

Queremos saber cuántas veces se ejecuta el bucle para saber cuánto valdrá `var1` al final.

- **Paso 1: ¿Cuántas veces se suma 0xcb?**
    
    - Valor inicial de `var2`: $0xf$ (15 decimal).
        
    - Valor objetivo: debe ser mayor que $0xd72d$ ($55085$ decimal).
        
    - Distancia a recorrer: $55085 - 15 = 55070$.
        
    - Incrementos de: $0xcb$ (203).
        
    - Operación: $55070 / 203 \approx 271.28$.
        
    - Esto significa que después de **272** iteraciones, `var2` por fin será mayor que $0xd72d$.
        
- **Paso 2: ¿Cuál es el valor final de `var1`?**
    
    - `var1` empezó en **0x17** (23 decimal).
        
    - En cada una de las **272** iteraciones, se le sumó **1**.
        
    - Resultado: $23 + 272 = 295$.
        
Conversión a Hexadecimal

Ahora pasamos el resultado decimal **295** a hexadecimal:

- $295 / 16 = 18$ con resto **7**
    
- $18 / 16 = 1$ con resto **2**
    
- $1 / 16 = 0$ con resto **1**
    
- Leyendo de abajo hacia arriba: **0x127**
    

---

Resultado Final

La función devuelve el valor de `var1` (`eax` en `<+44>`).

**Flag:** `0x127`

## NOTAS ADICIONALES

## REFERENCIAS