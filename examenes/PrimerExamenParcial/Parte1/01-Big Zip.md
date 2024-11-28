# Big Zip

## Objetivo
Unzip this archive and find the flag.

- [Download zip file](https://artifacts.picoctf.net/c/505/big-zip-files.zip)
## Pistas

| No. Pista | Pista                                                                               |
| --------- | ----------------------------------------------------------------------------------- |
| 1         | Can grep be instructed to look at every file in a directory and its subdirectories? |


## Solucion
```bash
┌──(kali㉿kali)-[~/Documents/parcial1]
└─$ grep -r "pico"     
big-zip-files/folder_pmbymkjcya/folder_cawigcwvgv/folder_ltdayfmktr/folder_fnpfclfyee/whzxrpivpqld.txt:information on the record will last a billion years. Genes and brains and books encode picoCTF{gr3p_15_m4g1c_ef8790dc}

```

## Notas adicionales

## Referencias