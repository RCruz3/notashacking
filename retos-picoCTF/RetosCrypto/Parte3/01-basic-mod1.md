# basic-mod1

## Objetivo
We found this weird message being passed around on the servers, we think we have a working decryption scheme.Download the message [here](https://artifacts.picoctf.net/c/128/message.txt).Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore.Wrap your decrypted message in the picoCTF flag format (i.e. `picoCTF{decrypted_message}`)

## Pistas

| No.  Pista | Pista                                                                                   |
| ---------- | --------------------------------------------------------------------------------------- |
| 1          | Do you know what `mod 37` means?                                                        |
| 2          | `mod 37` means modulo 37. It gives the remainder of a number after being divided by 37. |

## Solucion
```bash
┌──(kali㉿kali)-[~/Documentos/crypto/basicmod1]
└─$ wget https://artifacts.picoctf.net/c/128/message.txt
--2024-05-16 17:57:33--  https://artifacts.picoctf.net/c/128/message.txt
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.26, 3.161.55.61, 3.161.55.64, ...
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[3.161.55.26]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 84 [application/octet-stream]
Grabando a: «message.txt»

message.txt          100%[====================>]      84  --.-KB/s    en 0s      

2024-05-16 17:57:35 (89.7 MB/s) - «message.txt» guardado [84/84]

                                                                                  
┌──(kali㉿kali)-[~/Documentos/crypto/basicmod1]
└─$ ls          
message.txt
                                                                                  
┌──(kali㉿kali)-[~/Documentos/crypto/basicmod1]
└─$ cat message.txt 
165 248 94 346 299 73 198 221 313 137 205 87 336 110 186 69 223 213 216 216 177 138                                                                                   
┌──(kali㉿kali)-[~/Documentos/crypto/basicmod1]
└─$ nano exp.py                            
                                                                                  
┌──(kali㉿kali)-[~/Documentos/crypto/basicmod1]
└─$ python3 exp.py    
['165', '248', '94', '346', '299', '73', '198', '221', '313', '137', '205', '87', '336', '110', '186', '69', '223', '213', '216', '216', '177', '138']
picoCTF{R0UND_N_R0UND_B6B25531}

exp.py
atos = open('message.txt').read().split()

print (datos)

flag = ''

for n in datos:
     c = int(n) % 37
     if c>=0 and c <=25:
        s = chr(c+65)
     elif c >= 25 and c <= 35:
        s = chr(c+22)
     else:
        s = '_'
     flag += s
print(f"picoCTF{{{flag}}}")
```

## Notas adicionales

## Referencias