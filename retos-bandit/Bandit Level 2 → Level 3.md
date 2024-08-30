# Bandit Level 2 → Level 3

## Objetivo
The password for the next level is stored in a file called **spaces in this filename** located in the home directory
## Datos de acceso al nivel
```
bandit2
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
```
## Solucion
```bash
bandit2@bandit:~$ pwd
/home/bandit2
bandit2@bandit:~$ ls
spaces in this filename
bandit2@bandit:~$ cat "spaces in this filename" 
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
bandit2@bandit:~$
```

## Notas adicionales
|Commando| Descripcion|
|-----------|-------------|
|pwd| me indica el directorio actual|
|ls| lista los archivos de la carpeta actual|
|cat| me muestra el contenido del archivo|
* Cuando un archivo contiene espacios para poder accederlo se debe poner el nombre del archivo entre comillas o bien barra invertida en cada espacio

## Referencias
* [Google Search for “spaces in filename”](https://www.google.com/search?q=spaces+in+filename)