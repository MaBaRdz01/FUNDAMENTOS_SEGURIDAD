## RETO
asm3
## DESCRIPCION
What does asm3(0xb58568e8,0xc63ab2a1,0xf9d33ef4) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://challenge-files.picoctf.net/c_fickle_tempest/b3fee52f11c2963c3f6008623c66d7c0906ab439f927132ac7fbc1d53f83c4ee/test.S)
## SOLUCION

Los Parámetros

La función recibe tres valores de 32 bits:

1. `[ebp+0x8]` = `0xb58568e8`
    
2. `[ebp+0xc]` = `0xc63ab2a1`
    
3. `[ebp+0x10]` = `0xf9d33ef4`
    

Ejecución Paso a Paso

Para resolver esto, debemos visualizar el registro `eax` (de 32 bits) y sus divisiones: `ax` (16 bits), `ah` (8 bits superiores de `ax`) y `al` (8 bits inferiores de `ax`).

1. **`<+7> xor eax, eax`**:
    
    - Limpia el registro. `eax = 0x00000000`.
        
2. **`<+9> mov ah, BYTE PTR [ebp+0xb]`**:
    
    - Buscamos el byte en la posición `ebp + 0xb`.
        
    - El Arg1 está en `0x8, 0x9, 0xa, 0xb`. El valor es `0xb58568e8`.
        
    - Los bytes son: `[0x8]=e8`, `[0x9]=68`, `[0xa]=85`, `[0xb]=b5`.
        
    - Entonces, `ah = 0xb5`. Ahora `eax = 0x0000b500`.
        
3. **`<+12> shl ax, 0x10`**:
    
    - Desplaza `ax` (los 16 bits inferiores) 16 bits a la izquierda.
        
    - Como `ax` solo tiene 16 bits, cualquier desplazamiento de 16 bits hacia la izquierda lo deja en **0x0000**.
        
    - `eax` vuelve a ser `0x00000000`.
        
4. **`<+16> sub al, BYTE PTR [ebp+0xd]`**:
    
    - El Arg2 (`0xc63ab2a1`) empieza en `ebp+0xc`.
        
    - Bytes: `[0xc]=a1`, `[0xd]=b2`, `[0xe]=3a`, `[0xf]=c6`.
        
    - Restamos el byte de `0xd` (`b2`) a `al` (`00`).
        
    - `0x00 - 0xb2 = 0x4e` (esto es aritmética de 8 bits: `256 - 178 = 78` en decimal, que es `4e` en hex).
        
    - Ahora `eax = 0x0000004e`.
        
5. **`<+19> add ah, BYTE PTR [ebp+0xc]`**:
    
    - Sumamos el byte de `ebp+0xc` (`a1`) a `ah` (`00`).
        
    - `ah = 0xa1`.
        
    - Ahora `eax = 0x0000a14e`.
        
6. **`<+22> xor ax, WORD PTR [ebp+0x10]`**:
    
    - El Arg3 (`0xf9d33ef4`) está en `ebp+0x10`.
        
    - Como pide un **WORD** (16 bits), tomamos los dos primeros bytes: `f4` y `3e`. En formato _little-endian_ esto es `0x3ef4`.
        
    - Operación: `ax (0xa14e) XOR 0x3ef4`.
        

El Cálculo Final (XOR)

Plaintext

```
  1010 0001 0100 1110  (0xa14e)
^ 0011 1110 1111 0100  (0x3ef4)
---------------------
  1001 1111 1011 1010  (0x9fba)
```

**Resultado:** `0x9fba`### Los Parámetros

La función recibe tres valores de 32 bits:

1. `[ebp+0x8]` = `0xb58568e8`
    
2. `[ebp+0xc]` = `0xc63ab2a1`
    
3. `[ebp+0x10]` = `0xf9d33ef4`
    

Ejecución Paso a Paso

Para resolver esto, debemos visualizar el registro `eax` (de 32 bits) y sus divisiones: `ax` (16 bits), `ah` (8 bits superiores de `ax`) y `al` (8 bits inferiores de `ax`).

1. **`<+7> xor eax, eax`**:
    
    - Limpia el registro. `eax = 0x00000000`.
        
2. **`<+9> mov ah, BYTE PTR [ebp+0xb]`**:
    
    - Buscamos el byte en la posición `ebp + 0xb`.
        
    - El Arg1 está en `0x8, 0x9, 0xa, 0xb`. El valor es `0xb58568e8`.
        
    - Los bytes son: `[0x8]=e8`, `[0x9]=68`, `[0xa]=85`, `[0xb]=b5`.
        
    - Entonces, `ah = 0xb5`. Ahora `eax = 0x0000b500`.
        
3. **`<+12> shl ax, 0x10`**:
    
    - Desplaza `ax` (los 16 bits inferiores) 16 bits a la izquierda.
        
    - Como `ax` solo tiene 16 bits, cualquier desplazamiento de 16 bits hacia la izquierda lo deja en **0x0000**.
        
    - `eax` vuelve a ser `0x00000000`.
        
4. **`<+16> sub al, BYTE PTR [ebp+0xd]`**:
    
    - El Arg2 (`0xc63ab2a1`) empieza en `ebp+0xc`.
        
    - Bytes: `[0xc]=a1`, `[0xd]=b2`, `[0xe]=3a`, `[0xf]=c6`.
        
    - Restamos el byte de `0xd` (`b2`) a `al` (`00`).
        
    - `0x00 - 0xb2 = 0x4e` (esto es aritmética de 8 bits: `256 - 178 = 78` en decimal, que es `4e` en hex).
        
    - Ahora `eax = 0x0000004e`.
        
5. **`<+19> add ah, BYTE PTR [ebp+0xc]`**:
    
    - Sumamos el byte de `ebp+0xc` (`a1`) a `ah` (`00`).
        
    - `ah = 0xa1`.
        
    - Ahora `eax = 0x0000a14e`.
        
6. **`<+22> xor ax, WORD PTR [ebp+0x10]`**:
    
    - El Arg3 (`0xf9d33ef4`) está en `ebp+0x10`.
        
    - Como pide un **WORD** (16 bits), tomamos los dos primeros bytes: `f4` y `3e`. En formato _little-endian_ esto es `0x3ef4`.
        
    - Operación: `ax (0xa14e) XOR 0x3ef4`.
        

El Cálculo Final (XOR)

Plaintext

```
  1010 0001 0100 1110  (0xa14e)
^ 0011 1110 1111 0100  (0x3ef4)
---------------------
  1001 1111 1011 1010  (0x9fba)
```

**Resultado:** `0x9fba`
## NOTAS ADICIONALES

## REFERENCIAS