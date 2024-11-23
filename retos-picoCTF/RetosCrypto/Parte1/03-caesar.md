# caesar

## Objetivo
Decrypt this [message](https://jupiter.challenges.picoctf.org/static/49f31c8f17817dc2d367428c9e5ab0bc/ciphertext).

## Pistas

| No. Pistas | Pista                                                                                      |
| ---------- | ------------------------------------------------------------------------------------------ |
| 1          | caesar cipher [tutorial](https://learncryptography.com/classical-encryption/caesar-cipher) |


## Solucion
```
┌──(kali㉿kali)-[~/Documentos/crypto/caesar]
└─$ wget https://jupiter.challenges.picoctf.org/static/49f31c8f17817dc2d367428c9e5ab0bc/ciphertext 
--2024-04-16 11:03:20--  https://jupiter.challenges.picoctf.org/static/49f31c8f17817dc2d367428c9e5ab0bc/ciphertext
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 35 [application/octet-stream]
Grabando a: «ciphertext»

ciphertext               100%[================================>]      35  --.-KB/s    en 0s      

2024-04-16 11:03:20 (44.1 MB/s) - «ciphertext» guardado [35/35]

                                                                                                  
┌──(kali㉿kali)-[~/Documentos/crypto/caesar]
└─$ ls
ciphertext
                                                                                                  
┌──(kali㉿kali)-[~/Documentos/crypto/caesar]
└─$ file ciphertext  
ciphertext: ASCII text, with no line terminators
                                                                                                  
┌──(kali㉿kali)-[~/Documentos/crypto/caesar]
└─$ cat ciphertext                       
picoCTF{ynkooejcpdanqxeykjrbdofgkq}

Vamos a copiar lo de dentro de los corchetes y lo pegamos en cyberchef rot13, usamos como llave el 4 para que recorra 4 posiciones y asi quedaria:
picoCTF{crossingtherubiconvfhsjkou}


```

## Notas adicionales

## Referencias