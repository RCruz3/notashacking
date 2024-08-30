# Bandit Level 11 → Level 12

## Objetivo
The password for the next level is stored in the file **data.txt**, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

## Datos de acceso al nivel
```
bandit11
6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
```

## Solucion
```bash
bandit11@bandit:~$ ls
data.txt
bandit11@bandit:~$ cat data.txt 
Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi
bandit11@bandit:~$ cat data.txt | tr A-Za-z N-ZA-Mn-za-m
The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
bandit11@bandit:~$
```

## Notas adicionales
|Commando| Descripcion|
|-----------|-------------|
|ls| lista los archivos de la carpeta actual|
|tr|  reemplazar o eliminar un conjunto de caracteres de la Entrada estándar|
* A-Za-z N-ZA-Mn-za-m Simula el Rot13 haciendo una sustitucion de caracteres
## Referencias

* https://en.wikipedia.org/wiki/Rot13