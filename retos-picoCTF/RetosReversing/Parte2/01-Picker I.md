# 01-Picker I

## Objetivo
This service can provide you with a random number, but can it do anything else?Connect to the program with netcat:`$ nc saturn.picoctf.net 64628`The program's source code can be downloaded [here](https://artifacts.picoctf.net/c/514/picker-I.py).

## Pistas

| No. Pista | Pista                                                                       |
| --------- | --------------------------------------------------------------------------- |
| 1         | Can you point the program to a function that does something useful for you? |


## Solucion
```bash
┌──(kali㉿kali)-[~/Documentos/reversing]
└─$ wget https://artifacts.picoctf.net/c/514/picker-I.py
--2024-11-24 14:30:40--  https://artifacts.picoctf.net/c/514/picker-I.py
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 13.225.222.120, 13.225.222.105, 13.225.222.28, ...
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[13.225.222.120]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 3429 (3.3K) [application/octet-stream]
Grabando a: «picker-I.py»

picker-I.py              100%[==================================>]   3.35K  --.-KB/s    en 0s      

2024-11-24 14:30:41 (29.4 MB/s) - «picker-I.py» guardado [3429/3429]

                                                                                                    
┌──(kali㉿kali)-[~/Documentos/reversing]
└─$ nc saturn.picoctf.net 64628  
Try entering "getRandomNumber" without the double quotes...
==> win
0x70 0x69 0x63 0x6f 0x43 0x54 0x46 0x7b 0x34 0x5f 0x64 0x31 0x34 0x6d 0x30 0x6e 0x64 0x5f 0x31 0x6e 0x5f 0x37 0x68 0x33 0x5f 0x72 0x30 0x75 0x67 0x68 0x5f 0x36 0x65 0x30 0x34 0x34 0x34 0x30 0x64 0x7d 
Try entering "getRandomNumber" without the double quotes...

*Pasamos a CyberChef (From Hex)...
picoCTF{4_d14m0nd_1n_7h3_r0ugh_6e04440d}
```

## Notas adicionales

## Referencias