# fixme2.py

## Objetivo
Fix the syntax error in the Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/5/fixme2.py)

## Pistas

| No. Pista | Pista                                                                             |
| --------- | --------------------------------------------------------------------------------- |
| 1         | Are equality and assignment the same symbol?                                      |
| 2         | To view the file in the webshell, do: `$ nano fixme2.py`                          |
| 3         | To exit `nano`, press Ctrl and x and follow the on-screen prompts.                |
| 4         | The `str_xor` function does not need to be reverse engineered for this challenge. |


## Solucion
```bash
──(kali㉿kali)-[~/Descargas]
└─$ python3 fixme2.py                               
  File "/home/kali/Descargas/fixme2.py", line 22
    if flag = "":
       ^^^^^^^^^
SyntaxError: invalid syntax. Maybe you meant '==' or ':=' instead of '='?
                                                                                                  
┌──(kali㉿kali)-[~/Descargas]
└─$ nano fixme2.py   
                                                                                                  
┌──(kali㉿kali)-[~/Descargas]
└─$ python3 fixme2.py
That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_4863e11b}

***Codigo Corregido***
import random



def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,ne>


flag_enc = chr(0x15) + chr(0x07) + chr(0x08) + chr(0x06) + chr(0x27) + chr(0x21) + chr(0x23) + ch>

  
flag = str_xor(flag_enc, 'enkidu')

# Check that flag is not empty
if flag == "":
  print('String XOR encountered a problem, quitting.')
else:
  print('That is correct! Here\'s your flag: ' + flag)f
```

## Notas adicionales

## Referencias