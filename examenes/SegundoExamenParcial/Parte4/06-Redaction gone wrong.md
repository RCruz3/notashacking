# Redaction gone wrong

## Objetivo
Now you DON’T see me.This [report](https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf) has some critical data in it, some of which have been redacted correctly, while some were not. Can you find an important key that was not redacted properly?

## Pistas

| No. Pistas | Pista                                 |
| ---------- | ------------------------------------- |
| 1          | How can you be sure of the redaction? |

## Solucion
```bash
┌──(kali㉿kali)-[~/Documentos/forensic/redactiongonewrong]
└─$ wget https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf
--2024-04-09 16:52:52--  https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.21.46, 13.249.21.85, 13.249.21.32, ...
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[13.249.21.46]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 34915 (34K) [application/octet-stream]
Grabando a: «Financial_Report_for_ABC_Labs.pdf»

Financial_Report_for_ 100%[======================>]  34.10K  --.-KB/s    en 0.08s   

2024-04-09 16:52:55 (429 KB/s) - «Financial_Report_for_ABC_Labs.pdf» guardado [34915/34915]

                                                                                     
┌──(kali㉿kali)-[~/Documentos/forensic/redactiongonewrong]
└─$ file Financial_Report_for_ABC_Labs.pdf 
Financial_Report_for_ABC_Labs.pdf: PDF document, version 1.7, 1 pages
                                                                                 ┌──(kali㉿kali)-[~/Documentos/forensic/redactiongonewrong]
└─$ sudo apt-get install pdftohtml           
[sudo] contraseña para kali: 
Leyendo lista de paquetes... Hecho
Creando árbol de dependencias... Hecho
Leyendo la información de estado... Hecho
Nota, seleccionando «poppler-utils» en lugar de «pdftohtml»
Los paquetes indicados a continuación se instalaron de forma automática y ya no son necesarios.
  bluez-firmware firmware-ath9k-htc firmware-atheros firmware-brcm80211
  firmware-intel-sound firmware-libertas firmware-realtek firmware-sof-signed
  firmware-ti-connectivity firmware-zd1211 kali-linux-firmware
Utilice «sudo apt autoremove» para eliminarlos.
Se instalarán los siguientes paquetes NUEVOS:
  poppler-utils
0 actualizados, 1 nuevos se instalarán, 0 para eliminar y 1809 no actualizados.
Se necesita descargar 192 kB de archivos.
Se utilizarán 734 kB de espacio de disco adicional después de esta operación.
Des:1 http://http.kali.org/kali kali-rolling/main amd64 poppler-utils amd64 22.12.0-2+b1 [192 kB]
Descargados 192 kB en 7s (28.7 kB/s)            
Seleccionando el paquete poppler-utils previamente no seleccionado.
(Leyendo la base de datos ... 399029 ficheros o directorios instalados actualmente.)
Preparando para desempaquetar .../poppler-utils_22.12.0-2+b1_amd64.deb ...
Desempaquetando poppler-utils (22.12.0-2+b1) ...
Configurando poppler-utils (22.12.0-2+b1) ...
Procesando disparadores para man-db (2.11.2-2) ...
Procesando disparadores para kali-menu (2023.1.7) ...
                                                                                     
┌──(kali㉿kali)-[~/Documentos/forensic/redactiongonewrong]
└─$ lesspipe Financial_Report_for_ABC_Labs.pdf
Financial Report for ABC Labs, Kigali, Rwanda for the year 2021.

Breakdown - Just painted over in MS word.




Cost Benefit Analysis

Credit Debit

This is not the flag, keep looking

Expenses from the

picoCTF{C4n_Y0u_S33_m3_fully}

Redacted document.    
```

## Notas adicionales

## Referencias