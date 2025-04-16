## Descripción
Connect to this PostgreSQL server and find the flag!

Additional details will be available after launching your challenge instance.

Hints:
1. What does a SQL database contain?

## Solución 

Para este reto se tiene que conectar a una base de datos y buscar la bandera dentro de las tablas disponibles

```
SrRiv-picoctf@webshell:~$ psql -h saturn.picoctf.net -p 60557 -U postgres pico
Password for user postgres: 
psql (14.17 (Ubuntu 14.17-0ubuntu0.22.04.1), server 15.2 (Debian 15.2-1.pgdg110+1))
WARNING: psql major version 14, server major version 15.
         Some psql features might not work.
Type "help" for help.

```
Una vez establecida la conexión podemos listar las bases de datos.
```
pico=# \x
Expanded display is on.
pico=# \list
List of databases
-[ RECORD 1 ]-----+----------------------
Name              | pico
Owner             | postgres
Encoding          | UTF8
Collate           | en_US.utf8
Ctype             | en_US.utf8
Access privileges | 
-[ RECORD 2 ]-----+----------------------
Name              | postgres
Owner             | postgres
Encoding          | UTF8
Collate           | en_US.utf8
Ctype             | en_US.utf8
Access privileges | 
-[ RECORD 3 ]-----+----------------------
Name              | template0
Owner             | postgres
Encoding          | UTF8
Collate           | en_US.utf8
Ctype             | en_US.utf8
Access privileges | =c/postgres          +
                  | postgres=CTc/postgres
-[ RECORD 4 ]-----+----------------------
Name              | template1
Owner             | postgres
Encoding          | UTF8
Collate           | en_US.utf8
Ctype             | en_US.utf8
Access privileges | =c/postgres          +
                  | postgres=CTc/postgres
```
Y realizamos la conexión a la base de pico
```
pico=# \c pico
psql (14.17 (Ubuntu 14.17-0ubuntu0.22.04.1), server 15.2 (Debian 15.2-1.pgdg110+1))
WARNING: psql major version 14, server major version 15.
         Some psql features might not work.
You are now connected to database "pico" as user "postgres".
pico=# \dt
List of relations
-[ RECORD 1 ]----
Schema | public
Name   | flags
Type   | table
Owner  | postgres
```
Visualizamos la tabla de flags:
```
pico=# \d flags
                        Table "public.flags"
  Column   |          Type          | Collation | Nullable | Default 
-----------+------------------------+-----------+----------+---------
 id        | integer                |           | not null | 
 firstname | character varying(255) |           |          | 
 lastname  | character varying(255) |           |          | 
 address   | character varying(255) |           |          | 
Indexes:
    "flags_pkey" PRIMARY KEY, btree (id)
```
Y finalmente vemos todos los datos de dicha tabla, en donde encontraremos la bandera.
```
pico=# select * from flags;
-[ RECORD 1 ]-------------------------------------
id        | 1
firstname | Luke
lastname  | Skywalker
address   | picoCTF{L3arN_S0m3_5qL_t0d4Y_31fd14c0}
-[ RECORD 2 ]-------------------------------------
id        | 2
firstname | Leia
lastname  | Organa
address   | Alderaan
-[ RECORD 3 ]-------------------------------------
id        | 3
firstname | Han
lastname  | Solo
address   | Corellia

```


```
picoCTF{L3arN_S0m3_5qL_t0d4Y_31fd14c0}
```
## Notas adicionales 
## Referencias
https://www.youtube.com/watch?v=ar34AcZ5I3Y
