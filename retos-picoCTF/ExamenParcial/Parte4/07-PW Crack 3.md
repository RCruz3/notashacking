# PW Crack 3

## Objetivo
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/17/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/17/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/17/level3.hash.bin) in the same directory too.There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.

## Pistas

| No. Pista | Pista                                                                             |
| --------- | --------------------------------------------------------------------------------- |
| 1         | To view the level3.hash.bin file in the webshell, do: `$ bvi level3.hash.bin`     |
| 2         | To exit `bvi` type `:q` and press enter.                                          |
| 3         | The `str_xor` function does not need to be reverse engineered for this challenge. |


## Solucion
```bash
┌──(kali㉿kali)-[~/Descargas]
└─$ python3 level3.py
Please enter correct password for flag: f159
That password is incorrect
                                                                  
┌──(kali㉿kali)-[~/Descargas]
└─$ python3 level3.py
Please enter correct password for flag: 4dcf
That password is incorrect
                                                                  
┌──(kali㉿kali)-[~/Descargas]
└─$ python3 level3.py
Please enter correct password for flag: 3961
That password is incorrect
                                                                  
┌──(kali㉿kali)-[~/Descargas]
└─$ python3 level3.py
Please enter correct password for flag: 87ab
Welcome back... your flag, user:
picoCTF{m45h_fl1ng1ng_cd6ed2eb}
```

## Notas adicionales

## Referencias