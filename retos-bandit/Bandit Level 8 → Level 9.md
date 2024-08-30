# Bandit Level 8 → Level 9

## Objetivo
The password for the next level is stored in the file **data.txt** and is the only line of text that occurs only once
## Datos de acceso al nivel
```
bandit8
TESKZC0XvTetK0S9xNwm25STk5iWrBvP
```
## Solucion
```bash
bandit8@bandit:~$ 
bandit8@bandit:~$ ls
data.txt
bandit8@bandit:~$ sort data.txt | uniq -u
EN632PlfYiZbn3PhVK3XOGSlNInNE00t
bandit8@bandit:~$
```
## Notas adicionales
|Commando| Descripcion|
|-----------|-------------|
|ls| lista los archivos de la carpeta actual|
|sort| ordena las lineas de un archivo |
|uniq | quita las lineas que estan repetidas|
* El parámetro "u" (-u) del comando uniq sirve para mostrar las lineas que no estan repetidas

## Referencias