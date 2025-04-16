
###### Descripción:
If you want to hash with the best, beat this test!

Additional details will be available after launching your challenge instance.

If you want to hash with the best, beat this test!`nc saturn.picoctf.net 55960`


###### Pistas:

-You can use a commandline tool or web app to hash text
-Press Ctrl and c on your keyboard to close your connection and return to the command prompt.



**Solución 1**

```
En kali linux:

┌──(kali㉿kali)-[~]
└─$ nc saturn.picoctf.net 55960
Please md5 hash the text between quotes, excluding the quotes: 'Claude Monet'
Answer: 

-----------------------------------------------------------------------------------

Ir a cyberchef con la palabra que está dentro de las comillas simples, este proceso se hace 3 veces porque te pide 3 palabras para que te dé la bandera, el valor obtenido ponerlo como respuesta en la consola.

En cyberchef:

Input: Claude Monet

Recipe: 
	MD5

Output: 5c37529dab98927d2f3a8da6e8205dcd

-----------------------------------------------------------------------------------

Input: Joan of Arc

Recipe: 
	MD5

Output: 19ba425a542946fcf13228d9ddd53139

-----------------------------------------------------------------------------------


Input: a treehouse

Recipe: 
	MD5

Output: 98b0ee4dfd8e04322c60bd32481b512e

```


## Respuesta: **picoCTF{4ppl1c4710n_r3c31v3d_bf2ceb02}**


###### Referencias: https://gchq.github.io/CyberChef/