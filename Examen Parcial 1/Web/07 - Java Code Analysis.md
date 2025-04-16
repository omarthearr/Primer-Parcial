## Descripción:
BookShelf Pico, my premium online book-reading service.I believe that my website is super secure. I challenge you to prove me wrong by reading the 'Flag' book!Here are the credentials to get you started:

- Username: "user"
- Password: "user"

Source code can be downloaded [here](https://artifacts.picoctf.net/c/481/bookshelf-pico.zip).Website can be accessed [here!](http://saturn.picoctf.net:57346/).

Hints:
- Maybe try to find the JWT Signing Key ("secret key") in the source code? Maybe it's hardcoded somewhere? Or maybe try to crack it?
- The 'role' and 'userId' fields in the JWT can be of interest to you!
- The 'controllers', 'services' and 'security' java packages in the given source code might need your attention. We've provided a README.md file that contains some documentation.
- Upgrade your 'role' with the _new_ (cracked) JWT. And re-login for the new role to get reflected in browser's localStorage.

## Solución:
```
Este:
{
  "role": "Free",
  "iss": "bookshelf",
  "exp": 1745378781,
  "iat": 1744773981,
  "userId": 1,
  "email": "user"
}
Se modificó y quedó así:
{
  "role": "Admin",
  "iss": "bookshelf",
  "exp": 1745378781,
  "iat": 1744773981,
  "userId": 2,
  "email": "admin"
}


picoCTF{w34k_jwt_n0t_g00d_ca4d9701}
```

## Notas:
En una parte del código de SecretGenerator.java se ve que la llave de JWT es "1234", después en el navegador en Application en Local Storage está la key auth-token para modificarla en JWT.io y cambiar los valores para que al actualizar la página ya me dejara ver el libro de FLAG
