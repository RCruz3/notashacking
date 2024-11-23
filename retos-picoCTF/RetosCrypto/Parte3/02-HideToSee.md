# HideToSee

## Objetivo
How about some hide and seek heh?Look at this image [here](https://artifacts.picoctf.net/c/237/atbash.jpg).

## Pistas

| No.  Pista | Pista                                     |
| ---------- | ----------------------------------------- |
| 1          | Download the image and try to extract it. |

## Solucion
```bash
┌──(kali㉿kali)-[~/Documentos/crypto/hidetosee]
└─$ wget https://artifacts.picoctf.net/c/237/atbash.jpg 
--2024-05-16 18:06:41--  https://artifacts.picoctf.net/c/237/atbash.jpg
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.61, 3.161.55.26, 3.161.55.64, ...
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[3.161.55.61]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 51508 (50K) [application/octet-stream]
Grabando a: «atbash.jpg»

atbash.jpg           100%[====================>]  50.30K  --.-KB/s    en 0.1s    

2024-05-16 18:06:43 (450 KB/s) - «atbash.jpg» guardado [51508/51508]

                                                                                  
┌──(kali㉿kali)-[~/Documentos/crypto/hidetosee]
└─$ open atbash.jpg

* Subimos la imagen en: https://futureboy.us/stegano/decinput.html 
* Nos da el siguiente texto: krxlXGU{zgyzhs_xizxp_05y2z65z}
* Copiamos el texto y lo mandamos a cyberchef atbash cypher: https://gchq.github.io/CyberChef/#recipe=Atbash_Cipher()&input=a3J4bFhHVXt6Z3l6aHNfeGl6eHBfMDV5Mno2NXp9&oenc=65001&ieol=CRLF
* Nos dara la bandera: picoCTF{atbash_crack_05b2a65a}
```

## Notas adicionales

## Referencias