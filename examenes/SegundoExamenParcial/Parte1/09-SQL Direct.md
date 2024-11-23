# SQL Direct

## Objetivo
Connect to this PostgreSQL server and find the flag!

Additional details will be available after launching your challenge instance.

## Pistas

| No. Pistas | Pista                             |
| ---------- | --------------------------------- |
| 1          | What does a SQL database contain? |


## Solucion
```bash
┌──(kali㉿kali)-[~]
└─$ psql -h saturn.picoctf.net -p 52535 -U postgres pico
Contraseña para usuario postgres: 
psql (15.2 (Debian 15.2-2))
Digite «help» para obtener ayuda.

pico=# help
Está usando psql, la interfaz de línea de órdenes de PostgreSQL.
Digite:  \copyright para ver los términos de distribución
       \h para ayuda de órdenes SQL
       \? para ayuda de órdenes psql
       \g o punto y coma («;») para ejecutar la consulta
       \q para salir
pico=# \h
pico=# \?
pico=# \d
        Listado de relaciones
 Esquema | Nombre | Tipo  |  Dueño   
---------+--------+-------+----------
 public  | flags  | tabla | postgres
(1 fila)

pico=# SELECT * FROM flags;
 id | firstname | lastname  |                address                 
----+-----------+-----------+----------------------------------------
  1 | Luke      | Skywalker | picoCTF{L3arN_S0m3_5qL_t0d4Y_31fd14c0}
  2 | Leia      | Organa    | Alderaan
  3 | Han       | Solo      | Corellia
(3 filas)

pico=# 

```

## Notas adicionales

## Referencias