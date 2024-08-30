# Bandit Level 7 → Level 8

## Objetivo
The password for the next level is stored in the file **data.txt** next to the word **millionth**

## Datos de acceso al nivel
```
bandit7
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
```
## Solucion
```bash
bandit7@bandit:~$ ls
data.txt
bandit7@bandit:~$ grep "millionth" data.txt
millionth       TESKZC0XvTetK0S9xNwm25STk5iWrBvP
bandit7@bandit:~$
```

## Notas adicionales
|Commando| Descripcion|
|-----------|-------------|
|ls| lista los archivos de la carpeta actual|
|grep| realiza una busqueda de contenido coincidente con el texto que se le indique|


## Referencias