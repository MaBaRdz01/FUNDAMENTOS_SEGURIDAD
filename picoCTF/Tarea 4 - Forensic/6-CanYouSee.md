## RETO
CanYouSee
## DESCRIPCION
How about some hide and seek?Download this file [here](https://artifacts.picoctf.net/c_titan/4/unknown.zip).
## SOLUCION
PS C:\Users\maria\Downloads> Expand-Archive -Path .\unknown.zip -DestinationPath .\CanYouSee_Files
PS C:\Users\maria\Downloads> cd .\CanYouSee_Files
PS C:\Users\maria\Downloads\CanYouSee_Files> ls -Recurse


    Directorio: C:\Users\maria\Downloads\CanYouSee_Files


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----     15/02/2024  10:40 p. m.        2263765 ukn_reality.jpg


PS C:\Users\maria\Downloads\CanYouSee_Files> # Este comando busca cadenas sospechosas en el archivo
PS C:\Users\maria\Downloads\CanYouSee_Files> strings.exe .\nombre_de_la_imagen.jpg | Select-String -Pattern "[A-Za-z0-9+/]{20,}=="
C:\Program Files\mingw-w64\x86_64-8.1.0-posix-seh-rt_v6-rev0\mingw64\bin\strings.exe: '.\nombre_de_la_imagen.jpg': No such file
PS C:\Users\maria\Downloads\CanYouSee_Files> strings.exe .\ukn_reality.jpg | Select-String -Pattern "[A-Za-z0-9+/]{20,}=="

  <cc:attributionURL
rdf:resource='cGljb0NURntNRTc0RDQ3QV9ISUREM05fZGVjYTA2ZmJ9Cg=='/>


PS C:\Users\maria\Downloads\CanYouSee_Files> [System.Text.Encoding]::UTF8.GetString([System.Convert]::FromBase64String("cGljb0NURntNRTc0RDQ3QV9ISUREM05fZGVjYTA2ZmJ9Cg=="))
picoCTF{ME74D47A_HIDD3N_deca06fb}

## NOTAS ADICIONALES

## REFERENCIAS