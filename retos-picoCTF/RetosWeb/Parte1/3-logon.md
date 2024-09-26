# logon
## Objetivo
The factory is hiding things from all of its users. Can you login as Joe and find what they've been looking at? `https://jupiter.challenges.picoctf.org/problem/15796/` ([link](https://jupiter.challenges.picoctf.org/problem/15796/)) or http://jupiter.challenges.picoctf.org:15796

## Pistas

| No. Pista | Pista                                                             |
| --------- | ----------------------------------------------------------------- |
| 1         | Hmm it doesn't seem to check anyone's password, except for Joe's? |

## Solucion
```
- Primero: Abrimos el link que nos muestra en el reto.
- Segundo: Ingresaos cualquier usuario exepto Joe y le damos cualquier ontraseña.
- Tercero: Le damos click derecho y seleccionamos inspeccionar.
- Cuarto: Se abrirá una barra y seleccionaremos en el apartado de "Almacenamiento".
- Quinto: En el apartado de donde se ingreso el usuario en la columna del valor cambiamos 'False' por 'True' recargamos la paguina y nos da la bandera.

`picoCTF{th3_c0nsp1r4cy_l1v3s_6edb3f5f}`
```

## Notas adicionales

## Referencias