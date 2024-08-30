# Bandit Level 6 → Level 7

## Objetivo
The password for the next level is stored **somewhere on the server** and has all of the following properties:

- owned by user bandit7
- owned by group bandit6
- 33 bytes in size

## Datos de acceso al nivel
```
bandit6
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
```

## Solucion
```bash
bandit6@bandit:~$ find / -user "bandit7" -and -group "bandit6" -and -size 33c 2>/dev/null
/var/lib/dpkg/info/bandit7.password
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
bandit6@bandit:~$
```

## Notas adicionales
|Commando| Descripcion|
|-----------|-------------|
|ls| lista los archivos de la carpeta actual|
|find| realiza una busqueda de archivos segun los parametros indicados|
|cat| me muestra el contenido del archivo|
* El parametro "user" (-user) se usa para indicar que se busque archivos creados por un usuario especifico
* El parametro "group" (-group) se usa para indicar que se busque archivos creados por un grupo especifico
* Se pueden usar otros parametros como and (-and), or (-or) y not (-not) para combinar varios
## Referencias