# Bandit Level 3 → Level 4

## Objetivo
The password for the next level is stored in a hidden file in the **inhere** directory.
## Datos de acceso al nivel
```
bandit3
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
```
## Solucion
```bash
bandit3@bandit:~$ ls
inhere
bandit3@bandit:~$ cd inhere
bandit3@bandit:~/inhere$ ls
bandit3@bandit:~/inhere$ ls -a
.  ..  .hidden
bandit3@bandit:~/inhere$ cat .hidden
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
bandit3@bandit:~/inhere$ cd
bandit3@bandit:~$
```

## Notas adicionales
|Commando| Descripcion|
|-----------|-------------|
|ls| lista los archivos de la carpeta actual|
|cat| me muestra el contenido del archivo|
* Para poder ver los archivos ocultos se debe agregar el parametro "a" al comando ls (ls -a) y seguidamente el nombre del archivo


## Referencias
* Me acorde de la clase de LInux
