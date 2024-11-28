# repetitions

## Objetivo
Can you make sense of this file?Download the file [here](https://artifacts.picoctf.net/c/476/enc_flag).

## Pistas

| No. Pista | Pista                             |
| --------- | --------------------------------- |
| 1         | Multiple decoding is always good. |


## Solucion
```bash
┌──(kali㉿kali)-[~/Documents/parcial1]
└─$ file enc_flag                  
enc_flag: ASCII text
                                                           
┌──(kali㉿kali)-[~/Documents/parcial1]
└─$ cat enc_flag 
VmpGU1EyRXlUWGxTYmxKVVYwZFNWbGxyV21GV1JteDBUbFpPYWxKdFVsaFpWVlUxWVZaS1ZWWnVh
RmRXZWtab1dWWmtSMk5yTlZWWApiVVpUVm10d1VWZFdVa2RpYlZaWFZtNVdVZ3BpU0VKeldWUkNk
MlZXVlhoWGJYQk9VbFJXU0ZkcVRuTldaM0JZVWpGS2VWWkdaSGRXCk1sWnpWV3hhVm1KRk5XOVVW
VkpEVGxaYVdFMVhSbFZrTTBKVVZXMTRWMDVHV2toalJYUlhDazFyV25sVVZXaHpWakpHZEdWRlZs
aGkKYlRrelZERldUMkpzUWxWTlJYTkxDZz09Cg==
```
* En CyberChef (From Base64(6))
picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_4557ec3e}

## Notas adicionales

## Referencias