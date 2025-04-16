
###### Descripción:
Welcome to the challenge! In this challenge, you will explore a web application and find an endpoint that exposes a file containing a hidden flag.The application is a simple blog website where you can read articles about various topics, including an article about API Documentation. Your goal is to explore the application and find the endpoint that generates files holding the server’s memory, where a secret flag is hidden.

The website is running [picoCTF News](http://verbal-sleep.picoctf.net:50116/).


###### Pistas:

-Explore backend development with us.
-The head was dumped.



**Solución 1**

```
En un navegador abrir la página web:

-Dar click al link que dice "#API Documentation"

-En el apartado de "Diagnosing" dar click al botón GET que pertenece a /headump
-Dar click al botón "try it out"
-Dar click al botón "execute"
-Dar click al enlace "Download file"

----------------------------------------------------------------------------------

En la consola de comandos:

-Ir a la ruta donde se descargó el archivo


┌──(kali㉿kali)-[~/Downloads]
└─$ cat heapdump-1744762231341.heapsnapshot | grep "picoCTF"    

picoCTF{Pat!3nt_15_Th3_K3y_305d5b9a}
"picoCTF News API",
"Welcome to the picoCTF News API documentation! This documentation provides a detailed overview of the available API endpoints for managing and retrieving news posts.",
"\nwindow.onload = function() {\n  // Build a system\n  var url = window.location.search.match(/url=([^&]+)/);\n  if (url && url.length > 1) {\n    url = decodeURIComponent(url[1]);\n  } else {\n    url = window.location.origin;\n  }\n  var options = {\n  \"swaggerDoc\": {\n    \"openapi\": \"3.0.0\",\n    \"info\": {\n      \"title\": \"picoCTF News API\",\n      \"version\": \"1.0.0\",\n      \"description\": \"Welcome to the picoCTF News API documentation! This documentation provides a detailed overview of the available API endpoints for managing and retrieving news posts.\"\n    },\n    \"paths\": {\n      \"/\": {\n        \"get\": {\n          \"tags\": [\n            \"Free\"\n          ],\n          \"summary\": \"Welcome page\",\n          \"responses\": {\n            \"200\": {\n              \"description\": \"Returns a welcome message.\"\n            }\n          }\n        }\n      },\n      \"/about\": {\n        \"get\": {\n          \"tags\": [\n            \"Free\"\n          ],\n          \"summary\": \"About Us\",\n          \"responses\": {\n            \"200\": {\n              \"desc",
                  

```


## Respuesta: **picoCTF{Pat!3nt_15_Th3_K3y_305d5b9a}**


###### Referencias: 
**[https://www.youtube.com/watch?v=ks60T3_ccAo](https://www.youtube.com/watch?v=ks60T3_ccAo)**
