# where are the robots

## Objetivo
Can you find the robots? `https://jupiter.challenges.picoctf.org/problem/60915/` ([link](https://jupiter.challenges.picoctf.org/problem/60915/)) or http://jupiter.challenges.picoctf.org:60915

## Pistas

| No. Pista | Pista                                                                               |
| --------- | ----------------------------------------------------------------------------------- |
| 1         | What part of the website could tell you where the creator doesn't want you to look? |

## Solucion
```
- Primero: Abrimos el link que nos aparece en el reto.
- Segundo: En la barra donde va el link de navegación le agregamos robots.txt 
	https://jupiter.challenges.picoctf.org/problem/36474/robots.txt
- Tercero: Nos va a cargar una paguina con unos datos y lo copiamos (En mi caso fue: /8028f.html)
- Cuarto: Borramos lo que agregamos al link "robots.txt" y le pegamos lo que copiamos ahi mismo 
	https://jupiter.challenges.picoctf.org/problem/36474/8028f.html
Y nos dara la bandera

picoCTF{ca1cu1at1ng_Mach1n3s_477ce}
```

## Notas adicionales

## Referencias