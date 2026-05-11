## RETO
asm1
## DESCRIPCION
What does asm1(0x2ff) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://challenge-files.picoctf.net/c_fickle_tempest/936da3d33f13bd9c9153ad7e9974c2fe51c00da410fa43567caa790ed56f9346/test.S)
## SOLUCION

Análisis del Flujo de Ejecución

El argumento de entrada es `[ebp+0x8] = 0x2ff`.

1. **Comparación inicial (`<+7>`):** `cmp 0x2ff, 0x753`
    
    - ¿Es $0x2ff$ mayor que $0x753$? **No**. ($767 < 1875$ en decimal).
        
    - La instrucción `jg <asm1+41>` **no se toma**.
        
2. **Segunda comparación (`<+16>`):** `cmp 0x2ff, 0x5af`
    
    - ¿Es $0x2ff$ diferente de $0x5af$? **Sí**.
        
    - La instrucción `jne <asm1+33>` **se ejecuta**, por lo que saltamos a la dirección `<+33>`.
        
3. **Bloque de código en `<+33>`:**
    
    - `mov eax, DWORD PTR [ebp+0x8]`: El registro `eax` ahora vale **$0x2ff$**.
        
    - `sub eax, 0x7`: Restamos $7$ al valor.
        
    - Operación: $0x2ff - 0x7 = 0x2f8$.
        
4. **Salto final (`<+39>`):**
    
    - `jmp <asm1+64>`: Saltamos directamente al final de la función.
        
5. **Retorno (`<+64>` y `<+65>`):**
    
    - Se restaura el puntero de base y se retorna el valor almacenado en `eax`.
        

---

Cálculo Matemático (Hexadecimal)

Para estar seguros del resultado en hexadecimal:

$0x2ff$ termina en $F$ ($15$ decimal).

$15 - 7 = 8$.

Por lo tanto, **$0x2ff - 0x7 = 0x2f8$**.

Resultado para el Flag

**0x2f8**


## NOTAS ADICIONALES

## REFERENCIAS