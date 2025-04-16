
**Descripción:**
The Rust saga continues? I ask you, can I borrow that, pleeeeeaaaasseeeee?Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/babfbee79718a6363826ba86300173ffde6d81577e9dd07d4130c53a7eecf6c3/fixme2.tar.gz).

**Hints:**
https://doc.rust-lang.org/book/ch04-02-references-and-borrowing.html


**Solución 1**

```
- Descargamos el archivo
- Descomprimimos el archivo
- Instalamos rust
- Nos ubicamos en el directorio fixme2
- Ejecutamos un cargo build
- Hacemos referencias mutables:
	- Cambiamos el &String por &mut String
	- Cambiamos el let, por let mut
- Obtenemos la flag corriendo el programa, cargo run
```


## Respuesta: **picoCTF{4r3_y0u_h4v1n5_fun_y31?}**
---
Referencias: 
- https://www.youtube.com/watch?v=zSwZRlPbG38
- https://www.youtube.com/watch?v=Ibn4yz2oOgM

