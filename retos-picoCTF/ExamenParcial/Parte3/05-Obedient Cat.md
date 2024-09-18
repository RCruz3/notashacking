# Obedient Cat

## Objetivo
This file has a flag in plain sight (aka "in-the-clear").

## Pistas
| No. Pista | Pista                                                                                                                                                                                         |
| --------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1         | Any hints about entering a command into the Terminal (such as the next one), will start with a '$'... everything after the dollar sign will be typed (or copy and pasted) into your Terminal. |
| 2         | To get the file accessible in your shell, enter the following in the Terminal prompt: `$ wget https://mercury.picoctf.net/static/217686fc11d733b80be62dcfcfca6c75/flag`                       |
| 3         | `$ man cat`                                                                                                                                                                                   |

## Solucion
```bash
┌──(kali㉿kali)-[~]
└─$ wget https://mercury.picoctf.net/static/217686fc11d733b80be62dcfcfca6c75/flag
--2024-02-28 12:37:50--  https://mercury.picoctf.net/static/217686fc11d733b80be62dcfcfca6c75/flag
Resolviendo mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Conectando con mercury.picoctf.net (mercury.picoctf.net)[18.189.209.142]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 34 [application/octet-stream]
Grabando a: «flag»

flag          100%      34  --.-KB/s    en 0s        

2024-02-28 12:37:58 (22.3 MB/s) - «flag» guardado [34/34]

                                                      
┌──(kali㉿kali)-[~]
└─$ man cat 
                                                      
┌──(kali㉿kali)-[~]
└─$ ls                            
Descargas    incremento.asm
Desktop      incremento.o
Documentos   Música
Escritorio   Plantillas
flag         Público
Imágenes     suma_incremento
inc          suma_incremento.asm
inc.asm      suma_incremento_decremento
inc_dec      suma_incremento_decremento.asm
inc_dec.asm  suma_incremento_decremento.o
inc_dec.o    suma_incremento.o
inc.o        Vídeos
incremento
                                                      
┌──(kali㉿kali)-[~]
└─$ cat flag      
picoCTF{s4n1ty_v3r1f13d_b5aeb3dd}

```


## Notas adicionales

## Referencias