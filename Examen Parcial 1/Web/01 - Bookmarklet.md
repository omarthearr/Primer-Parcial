
## Descripción

Why search for the flag when I can make a bookmarklet to print it for me?
Additional details will be available after launching your challenge instance.

Hints:
1. A bookmarklet is a bookmark that runs JavaScript instead of loading a webpage.
2. What happens when you click a bookmarklet?
3. Web browsers have other ways to run JavaScript too.
## Solución 

En este reto se nos da la oportunidad de lanzar una instancia para acceder a un sitio web. En la pagina web se nos da un código dentro de una caja de texto.

```
        javascript:(function() {
            var encryptedFlag = "àÒÆÞ¦È¬ëÙ£ÖÓÚåÛÑ¢ÕÓ¨ÍÕÄ¦í";
            var key = "picoctf";
            var decryptedFlag = "";
            for (var i = 0; i < encryptedFlag.length; i++) {
                decryptedFlag += String.fromCharCode((encryptedFlag.charCodeAt(i) - key.charCodeAt(i % key.length) + 256) % 256);
            }
            alert(decryptedFlag);
        })();
    
```

En este punto tenemos que entrar a inspeccionar la página y entrar al apartado de ``Consola``, en este apartado copiamos el código y obtenemos la bandera.

```
picoCTF{p@g3_turn3r_18d2fa20}
```
## Notas adicionales 
## Referencias
https://www.youtube.com/watch?v=9UdXmPlpEhk
