
**Description**
Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag!Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/dcdaf491b35c1d0f5075e9583edbbb7aaea1dffb6ad32bc000e4d87b5200ff7b/fixme3.tar.gz).

**Hints:**
Read the comments...darn it!


**Solución 1**

```
- Descargamos el archivo que es un tar
- Usamos tar -xvzf para descomprimir
- Nos vamos a la carpeta fixme3
- Hacemos un cargo build, para compilar el programa en rust
- Le descomentamos la función: unsafe, estaba comentada y el paréntesis que la cierra
- Corremo el programa con cargo run
- Obtenemos la bandera
```


## Respuesta: **picoCTF{now_y0uv3_f1x3d_1h3m_411}**

---
Referencias:
- https://www.youtube.com/watch?v=i2LzGYRqUbs
