# Bandit Level 5 → Level 6

## Objetivo
The password for the next level is stored in a file somewhere under the **inhere** directory and has all of the following properties:

- human-readable
- 1033 bytes in size
- not executable


## Datos de acceso al nivel
```
bandit5
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
```

## Solucion
```bash
bandit5@bandit:~$ ls
inhere
bandit5@bandit:~$ cd inhere
bandit5@bandit:~/inhere$ ls -l
total 80
drwxr-x--- 2 root bandit5 4096 Apr 23 18:04 maybehere00
drwxr-x--- 2 root bandit5 4096 Apr 23 18:04 maybehere01
drwxr-x--- 2 root bandit5 4096 Apr 23 18:04 maybehere02
drwxr-x--- 2 root bandit5 4096 Apr 23 18:04 maybehere03
drwxr-x--- 2 root bandit5 4096 Apr 23 18:04 maybehere04
drwxr-x--- 2 root bandit5 4096 Apr 23 18:04 maybehere05
drwxr-x--- 2 root bandit5 4096 Apr 23 18:04 maybehere06
drwxr-x--- 2 root bandit5 4096 Apr 23 18:04 maybehere07
drwxr-x--- 2 root bandit5 4096 Apr 23 18:04 maybehere08
drwxr-x--- 2 root bandit5 4096 Apr 23 18:04 maybehere09
drwxr-x--- 2 root bandit5 4096 Apr 23 18:04 maybehere10
drwxr-x--- 2 root bandit5 4096 Apr 23 18:04 maybehere11
drwxr-x--- 2 root bandit5 4096 Apr 23 18:04 maybehere12
drwxr-x--- 2 root bandit5 4096 Apr 23 18:04 maybehere13
drwxr-x--- 2 root bandit5 4096 Apr 23 18:04 maybehere14
drwxr-x--- 2 root bandit5 4096 Apr 23 18:04 maybehere15
drwxr-x--- 2 root bandit5 4096 Apr 23 18:04 maybehere16
drwxr-x--- 2 root bandit5 4096 Apr 23 18:04 maybehere17
drwxr-x--- 2 root bandit5 4096 Apr 23 18:04 maybehere18
drwxr-x--- 2 root bandit5 4096 Apr 23 18:04 maybehere19
bandit5@bandit:~/inhere$ find . -size 1033c
./maybehere07/.file2
bandit5@bandit:~/inhere$ cd ./maybehere07/
bandit5@bandit:~/inhere/maybehere07$ cat .file2
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
bandit5@bandit:~/inhere/maybehere07$
```

## Notas adicionales
|Commando| Descripcion|
|-----------|-------------|
|ls| lista los archivos de la carpeta actual|
|find| realiza una busqueda de archivos segun los parametros indicados|
|cat| me muestra el contenido del archivo|
* Con el parametro size (-size) podemos indicarle el tamanio del archivo
	c = byte
	k = kilobyte
	M = megabyte
	G = gigabyte



## Referencias