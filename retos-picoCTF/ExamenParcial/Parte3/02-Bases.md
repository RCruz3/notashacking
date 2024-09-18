#  Bases

## Objetivo
What does this `bDNhcm5fdGgzX3IwcDM1` mean? I think it has something to do with bases.

## Pistas


| No. Pista | Pista                                                                                                                          |
| --------- | ------------------------------------------------------------------------------------------------------------------------------ |
| 1         | Submit your answer in our flag format. For example, if your answer was 'hello', you would submit 'picoCTF{hello}' as the flag. |

## Solucion
```bash
┌──(kali㉿kali)-[~]
└─$ python3
Python 3.11.4 (main, Jun  7 2023, 10:13:09) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import base64
>>> 
>>> encoded_string = "bDNhcm5fdGgzX3IwcDM1"
>>> decoded_string = base64.b64decode(encoded_string).decode('utf-8')
>>> print(decoded_string)
l3arn_th3_r0p35
>>> 

```

## Notas adicionales

## Referencias