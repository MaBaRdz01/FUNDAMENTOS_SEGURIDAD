## RETO
Wave a flag
## DESCRIPCION
Can you invoke help flags for a tool or binary? This program has extraordinarily helpful information...[warm](https://challenge-files.picoctf.net/c_wily_courier/89a0e56b3f2697fe5d597b2805202b86693dcb0e04aec062e11fe66edbbd04aa/warm)
## SOLUCION
1. Después de descargar el archivo, ejecutar el comando==file warm==
lo muestra como archivo ejecutable
2. Cuando intentemos ejecutarlo con ==./warm==  da un error y pueda ser que no tenga permisos.
3. Para dar permisos ==chmod +x warm==
4. Se vuelve a ejecutar
5. Finalmente ==./warm -h==


## NOTAS ADICIONALES

## REFERENCIAS

┌──(kali㉿kali)-[~/Downloads]
└─$ file warm
warm: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked8081bddcfe67, for GNU/Linux 3.2.0, with debug_info, not stripped
                                                                                 
┌──(kali㉿kali)-[~/Downloads]
└─$ ./warm
zsh: permission denied: ./warm
                                                                                 
┌──(kali㉿kali)-[~/Downloads]
└─$ chmod +x warm          
                                                                                 
┌──(kali㉿kali)-[~/Downloads]
└─$ ./warm       
Hello user! Pass me a -h to learn what I can do!
                                                                                 
┌──(kali㉿kali)-[~/Downloads]
└─$ ./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_ac5832c}


