# Bandit Level 1 → Level 2

## Objetivo
The password for the next level is stored in a file called **-** located in the home directory

## Datos de acceso al nivel
```
Bandit1
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
```

## Solucion
```bash
bandit1@bandit:~$ ls
-
bandit1@bandit:~$ cat -
^C
bandit1@bandit:~$ cat ./-
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
bandit1@bandit:~$ 
```

## Notas adicionales

|Commando| Descripcion|
|-----------|-------------|
|whoami| saber el usuario actual|
|pwd| me indica el directorio actual|
|ls| lista los archivos de la carpeta actual|
|cat| me muestra el contenido del archivo|
* Cuando un archivo comienza con un - (guion) para poder accederlo tenemos que anteponer ./ al nombre, o bien especificar la ruta completa al archivo*
## Referencias
* https://www.google.com/search?q=dashed+filename