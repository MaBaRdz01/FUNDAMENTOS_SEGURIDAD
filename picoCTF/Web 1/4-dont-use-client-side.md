## RETO
dont-use-client-side
## DESCRIPCION
Can you break into this super secure portal? http://fickle-tempest.picoctf.net:55347
## SOLUCION
Lo primero obvio que hay que hacer, ya que nada más se menciona es mirar a la fuente de la página esperando que si podemos encontrar algo importante.
Nos dan un codigo en el cual se ve la bandera en muchos ifs y sin ordenar y seguiremos:
substring(0, split)
substring(split, split*2)
substring(split*2, split*3)
substring(split*3, split*4)
substring(split*4, split*5)
substring(split*5, split*6)
substring(split*6, split*7)
substring(split*7, split*8)


picoCTF{no_clients_Plz_2eb02b45}
## NOTAS ADICIONALES


## REFERENCIAS
- cliente - servidor : [https://www.educative.io/answers/client-side-vs-server-side](https://www.educative.io/answers/client-side-vs-server-side "https://www.educative.io/answers/client-side-vs-server-side")
- firefox depurador: [https://firefox-source-docs.mozilla.org/devtools-user/debugger/index.html](https://firefox-source-docs.mozilla.org/devtools-user/debugger/index.html "https://firefox-source-docs.mozilla.org/devtools-user/debugger/index.html")