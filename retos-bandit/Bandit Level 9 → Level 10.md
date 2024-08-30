# Bandit Level 9 → Level 10

## Objetivo
The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, preceded by several ‘=’ characters.
## Datos de acceso al nivel
```
bandit9
EN632PlfYiZbn3PhVK3XOGSlNInNE00t
```

## Solucion
```bash
bandit9@bandit:~$ ls
data.txt
bandit9@bandit:~$ strings -n 10 data.txt 
4========== the#
========== password
========== is
========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
bandit9@bandit:~$
```

## Notas adicionales
|Commando| Descripcion|
|-----------|-------------|
|ls| lista los archivos de la carpeta actual|
|strings| extrae cadenas de texto o caracteres imprimibles|
* El parametro "n" (-n) del comando strings nos ayuda a indicar la cantidad de caracteres que debe contener la o las cadenas que queremos extraer 


## Referencias