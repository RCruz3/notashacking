# What Lies Within
## Objetivo
There's something in the [building](https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png). Can you retrieve the flag?

## Pistas

| No. Pista | Pista                                                                |
| --------- | -------------------------------------------------------------------- |
| 1         | There is data encoded somewhere... there might be an online decoder. |


## Solucion
```bash
┌──(kali㉿kali)-[~/Documentos/forensic]
└─$ wget https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png
--2024-03-15 01:32:52--  https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 625219 (611K) [application/octet-stream]
Grabando a: «buildings.png»

buildings.png            100%[================================>] 610.57K  1.98MB/s    en 0.3s    

2024-03-15 01:32:52 (1.98 MB/s) - «buildings.png» guardado [625219/625219]

                                                                            
┌──(kali㉿kali)-[~/Documentos/forensic]
└─$ open buildings.png 
                                                                            
┌──(kali㉿kali)-[~/Documentos/forensic]
└─$ zsteg
zsteg: no se encontró la orden
                                                                            
┌──(kali㉿kali)-[~/Documentos/forensic]
└─$ sudo gem install zsteg                          
[sudo] contraseña para kali: 
Fetching rainbow-3.1.1.gem
Fetching iostruct-0.0.5.gem
Fetching zsteg-0.2.13.gem
Fetching zpng-0.4.5.gem
Successfully installed rainbow-3.1.1
Successfully installed zpng-0.4.5
Successfully installed iostruct-0.0.5
Successfully installed zsteg-0.2.13
Parsing documentation for rainbow-3.1.1
Installing ri documentation for rainbow-3.1.1
Parsing documentation for zpng-0.4.5
Installing ri documentation for zpng-0.4.5
Parsing documentation for iostruct-0.0.5
Installing ri documentation for iostruct-0.0.5
Parsing documentation for zsteg-0.2.13
Installing ri documentation for zsteg-0.2.13
Done installing documentation for rainbow, zpng, iostruct, zsteg after 5 seconds
4 gems installed
                                                                            
┌──(kali㉿kali)-[~/Documentos/forensic]
└─$ zsteg -a buildings.png | grep pico
b1,rgb,lsb,xy       .. text: "picoCTF{h1d1ng_1n_th3_b1t5}"
```

## Notas adicionales

## Referencias