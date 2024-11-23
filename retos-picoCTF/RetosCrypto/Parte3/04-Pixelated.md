# Pixelated

## Objetivo
I have these 2 images, can you make a flag out of them? [scrambled1.png](https://mercury.picoctf.net/static/1594c3f1980e3fb93df09a6d02f53904/scrambled1.png) [scrambled2.png](https://mercury.picoctf.net/static/1594c3f1980e3fb93df09a6d02f53904/scrambled2.png)

## Pistas

| No.  Pista | Pista                                                                                                  |
| ---------- | ------------------------------------------------------------------------------------------------------ |
| 1          | [https://en.wikipedia.org/wiki/Visual_cryptography](https://en.wikipedia.org/wiki/Visual_cryptography) |
| 2          | Think of different ways you can "stack" images                                                         |

## Solucion
```bash
┌──(kali㉿kali)-[~/Documentos/crypto/pixelated]
└─$ wget https://mercury.picoctf.net/static/1594c3f1980e3fb93df09a6d02f53904/scrambled1.png
--2024-05-16 19:40:50--  https://mercury.picoctf.net/static/1594c3f1980e3fb93df09a6d02f53904/scrambled1.png
Resolviendo mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Conectando con mercury.picoctf.net (mercury.picoctf.net)[18.189.209.142]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 197175 (193K) [application/octet-stream]
Grabando a: «scrambled1.png»

scrambled1.png       100%[====================>] 192.55K   748KB/s    en 0.3s    

2024-05-16 19:40:53 (748 KB/s) - «scrambled1.png» guardado [197175/197175]

                                                                                  
┌──(kali㉿kali)-[~/Documentos/crypto/pixelated]
└─$ wget https://mercury.picoctf.net/static/1594c3f1980e3fb93df09a6d02f53904/scrambled2.png
--2024-05-16 19:41:01--  https://mercury.picoctf.net/static/1594c3f1980e3fb93df09a6d02f53904/scrambled2.png
Resolviendo mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Conectando con mercury.picoctf.net (mercury.picoctf.net)[18.189.209.142]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 197172 (193K) [application/octet-stream]
Grabando a: «scrambled2.png»

scrambled2.png       100%[====================>] 192.55K   683KB/s    en 0.3s    

2024-05-16 19:41:02 (683 KB/s) - «scrambled2.png» guardado [197172/197172]

                                                                                  
┌──(kali㉿kali)-[~/Documentos/crypto/pixelated]
└─$ ls
scrambled1.png  scrambled2.png
                                                                                  
┌──(kali㉿kali)-[~/Documentos/crypto/pixelated]
┌──(kali㉿kali)-[~/Documentos/crypto/pixelated]
└─$ java -jar /opt/stegsolve.jar
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
----------------------------------------------------------------------
┌──(kali㉿kali)-[~]
└─$ cd /opt                 
                                                                                  
┌──(kali㉿kali)-[/opt]
└─$ sudo wget http://www.caesum.com/handbook/Stegsolve.jar -O stegsolve.jar
[sudo] contraseña para kali: 
--2024-05-16 19:58:26--  http://www.caesum.com/handbook/Stegsolve.jar
Resolviendo www.caesum.com (www.caesum.com)... 216.234.165.33
Conectando con www.caesum.com (www.caesum.com)[216.234.165.33]:80... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 312271 (305K) [application/x-java-archive]
Grabando a: «stegsolve.jar»

stegsolve.jar        100%[====================>] 304.95K   224KB/s    en 1.4s    

2024-05-16 19:58:28 (224 KB/s) - «stegsolve.jar» guardado [312271/312271]

                                                                                  
┌──(kali㉿kali)-[/opt]
└─$ sudo chmod +x stegsolve.jar 

* Abrimos stegsolve y combinamos las 2 imagenes, y en el resultado ADD nos da la bandera: picoCTF{1b867c3e}
```

## Notas adicionales

## Referencias