## Descripción:
Cookie Monster has hidden his top-secret cookie recipe somewhere on his website. As an aspiring cookie detective, your mission is to uncover this delectable secret. Can you outsmart Cookie Monster and find the hidden recipe?You can access the Cookie Monster [here](http://verbal-sleep.picoctf.net:49480/) and good luck

Hints:
- Sometimes, the most important information is hidden in plain sight. Have you checked all parts of the webpage?
- Cookies aren't just for eating - they're also used in web technologies!
- Web browsers often have tools that can help you inspect various aspects of a webpage, including things you can't see directly.

## Solución:
```
CyberChef recipe: FromBase64
input:cGljb0NURntjMDBrMWVfbTBuc3Rlcl9sMHZlc19jMDBraWVzX0FDOEZDRDc1fQ%3D%3D
output:picoCTF{c00k1e_m0nster_l0ves_c00kies_AC8FCD75}
ÃÜ
```

## Notas:
Con intentar iniciar sesión en la página, se genera una cookie que desifrando da la bandera

