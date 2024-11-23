# fixme1.py

## Objetivo
Fix the syntax error in this Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/26/fixme1.py)

## Pistas

| No. Pista | Pista                                                                             |
| --------- | --------------------------------------------------------------------------------- |
| 1         | Indentation is very meaningful in Python                                          |
| 2         | To view the file in the webshell, do: `$ nano fixme1.py`                          |
| 3         | To exit `nano`, press Ctrl and x and follow the on-screen prompts.                |
| 4         | The `str_xor` function does not need to be reverse engineered for this challenge. |


## Solucion
```bash
┌──(kali㉿kali)-[~/Descargas]
└─$ python3 fixme1.py
  File "/home/kali/Descargas/fixme1.py", line 19
    print('That is correct! Here\'s your flag: ' + flag)
IndentationError: unexpected indent
                                                                                                  
┌──(kali㉿kali)-[~/Descargas]
└─$ nano fixme1.py   
                                                                                                  
┌──(kali㉿kali)-[~/Descargas]
└─$ python3 fixme1.py
That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_09ee727a}

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
print('That is correct! Here\'s your flag: ' + flag)

```

## Notas adicionales

## Referencias