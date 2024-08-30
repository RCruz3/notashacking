# Bandit Level 10 → Level 11

## Objetivo
The password for the next level is stored in the file **data.txt**, which contains base64 encoded data

## Datos de acceso al nivel
```
bandit10
G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
```

## Solucion
```bash
bandit10@bandit:~$ ls
data.txt
bandit10@bandit:~$ base64 -d data.txt 
The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
bandit10@bandit:~$
```

## Notas adicionales
|Commando| Descripcion|
|-----------|-------------|
|ls| lista los archivos de la carpeta actual|
|base64|  decodifica el texto que esta en base64|

## Referencias
https://en.wikipedia.org/wiki/Base64