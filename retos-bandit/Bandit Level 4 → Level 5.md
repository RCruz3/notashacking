# Bandit Level 4 → Level 5

## Objetivo
The password for the next level is stored in the only human-readable file in the **inhere** directory. Tip: if your terminal is messed up, try the “reset” command.

## Datos de acceso al nivel
```
bandit4
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
```


## Solucion
```bash
bandit4@bandit:~$ ls
inhere
bandit4@bandit:~$ cd inhere/
bandit4@bandit:~/inhere$ ls -l
total 40
-rw-r----- 1 bandit5 bandit4 33 Apr 23 18:04 -file00
-rw-r----- 1 bandit5 bandit4 33 Apr 23 18:04 -file01
-rw-r----- 1 bandit5 bandit4 33 Apr 23 18:04 -file02
-rw-r----- 1 bandit5 bandit4 33 Apr 23 18:04 -file03
-rw-r----- 1 bandit5 bandit4 33 Apr 23 18:04 -file04
-rw-r----- 1 bandit5 bandit4 33 Apr 23 18:04 -file05
-rw-r----- 1 bandit5 bandit4 33 Apr 23 18:04 -file06
-rw-r----- 1 bandit5 bandit4 33 Apr 23 18:04 -file07
-rw-r----- 1 bandit5 bandit4 33 Apr 23 18:04 -file08
-rw-r----- 1 bandit5 bandit4 33 Apr 23 18:04 -file09
bandit4@bandit:~/inhere$ file ./*
./-file00: data
./-file01: data
./-file02: data
./-file03: data
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text
./-file08: data
./-file09: Non-ISO extended-ASCII text, with no line terminators
bandit4@bandit:~/inhere$ cat ./-file07
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
bandit4@bandit:~/inhere$
```

## Notas adicionales
|Commando| Descripcion|
|-----------|-------------|
|ls| lista los archivos de la carpeta actual|
|file| me indica de que tipo es el archivo|
|cat| me muestra el contenido del archivo|
* El asterisco sirve para indicar que el comando se ejecutara para todos los archivos que se encuentren en el directorio indicado

## Referencias