# Irish-Name-Repo 1

## Objetivo
There is a website running at `https://jupiter.challenges.picoctf.org/problem/50009/` ([link](https://jupiter.challenges.picoctf.org/problem/50009/)) or http://jupiter.challenges.picoctf.org:50009. Do you think you can log us in? Try to see if you can login!

## Pistas

| No.Pista | Pista                                                                                                   |
| -------- | ------------------------------------------------------------------------------------------------------- |
| 1        | There doesn't seem to be many ways to interact with this. I wonder if the users are kept in a database? |
| 2        | Try to think about how the website verifies your login.                                                 |


## Solucion
```
* Entramos a la página del reto y en el apartado del menu seleccionamos "Admin Login".
** En el user name ponemos ' or 1=1; que es un sql injection y en password el que sea.
```


## Notas adicionales

## Referencias