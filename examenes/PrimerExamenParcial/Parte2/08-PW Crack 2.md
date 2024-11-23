# PW Crack 2

## Objetivo
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/13/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/13/level2.flag.txt.enc) in the same directory too.

## Pistas

| No. Pista | Pista                                                                             |
| --------- | --------------------------------------------------------------------------------- |
| 1         | Does that encoding look familiar?                                                 |
| 2         | The `str_xor` function does not need to be reverse engineered for this challenge. |


## Solucion
```bash
┌──(kali㉿kali)-[~/Descargas]
└─$ nano level2.py                                          
                                                                                                  
┌──(kali㉿kali)-[~/Descargas]
└─$ nano script.py                          
┌──(kali㉿kali)-[~/Descargas]
└─$ python3 script.py
password: de76
                                                                                                  
┌──(kali㉿kali)-[~/Descargas]
└─$ python3 level2.py                                      
Please enter correct password for flag: de76
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_489dea9a}
```

## Notas adicionales

## Referencias