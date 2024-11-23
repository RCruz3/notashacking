# Vigenere

## Objetivo
Can you decrypt this message? Decrypt this [message](https://artifacts.picoctf.net/c/160/cipher.txt) using this key "CYLAB".
## Pistas

| No. Pista | Pista                                              |
| --------- | -------------------------------------------------- |
| 1         | https://en.wikipedia.org/wiki/Vigen%C3%A8re_cipher |


## Solucion
```bash
┌──(kali㉿kali)-[~/Documentos/crypto/vignere]
└─$ wget https://artifacts.picoctf.net/c/160/cipher.txt
--2024-05-20 15:41:01--  https://artifacts.picoctf.net/c/160/cipher.txt
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.100, 3.161.55.64, 3.161.55.26, ...
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[3.161.55.100]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 43 [application/octet-stream]
Grabando a: «cipher.txt»

cipher.txt               100%[================================>]      43  --.-KB/s    en 0s      

2024-05-20 15:41:02 (25.8 MB/s) - «cipher.txt» guardado [43/43]

                                                                                                  
┌──(kali㉿kali)-[~/Documentos/crypto/vignere]
└─$ ls
cipher.txt
                                                                                                  
┌──(kali㉿kali)-[~/Documentos/crypto/vignere]
└─$ cat cipher.txt 
rgnoDVD{O0NU_WQ3_G1G3O3T3_A1AH3S_2951c89f}

* mandamos el texto a cyberchef con la operacion de vigenere decode con "CYLAB" como llave: https://gchq.github.io/CyberChef/#recipe=Vigen%C3%A8re_Decode('CYLAB')&input=cmdub0RWRHtPME5VX1dRM19HMUczTzNUM19BMUFIM1NfMjk1MWM4OWZ9&ieol=CRLF&oeol=CRLF
* Conseguimos la bandera: picoCTF{D0NT_US3_V1G3N3R3_C1PH3R_2951a89h}

```

## Notas adicionales

## Referencias