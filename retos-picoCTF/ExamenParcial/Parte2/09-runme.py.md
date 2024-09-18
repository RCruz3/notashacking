# runme.py

## Objetivo
Run the `runme.py` script to get the flag. Download the script with your browser or with `wget` in the webshell.[Download runme.py Python script](https://artifacts.picoctf.net/c/34/runme.py)

## Pistas

| No. Pista | Pista                                                                                                                                                                                                        |
| --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 1         | If you have Python on your computer, you can download the script normally and run it. Otherwise, use the `wget` command in the webshell.                                                                     |
| 2         | To use `wget` in the webshell, first right click on the download link and select 'Copy Link' or 'Copy Link Address'                                                                                          |
| 3         | Type everything after the dollar sign in the webshell: `$ wget` , then paste the link after the space after `wget` and press enter. This will download the script for you in the webshell so you can run it! |
| 4         | Finally, to run the script, type everything after the dollar sign and then press enter: `$ python3 runme.py` You should have the flag now!                                                                   |


## Solucion
```bash
┌──(kali㉿kali)-[~/Descargas]
└─$ wget https://artifacts.picoctf.net/c/34/runme.py       
--2024-03-04 00:49:11--  https://artifacts.picoctf.net/c/34/runme.py
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.26, 3.161.55.100, 3.161.55.64, ...
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[3.161.55.26]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 270 [application/octet-stream]
Grabando a: «runme.py.1»

runme.py.1               100%[================================>]     270  --.-KB/s    en 0s      

2024-03-04 00:49:12 (168 MB/s) - «runme.py.1» guardado [270/270]

                                                                                                  
┌──(kali㉿kali)-[~/Descargas]
└─$ python3 runme.py               
picoCTF{run_s4n1ty_run}
```

## Notas adicionales

## Referencias