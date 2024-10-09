# c0rrupt

## Objetivo
We found this [file](https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery). Recover the flag.

## Pistas

| No. Pista | Pista                      |
| --------- | -------------------------- |
| 1         | Try fixing the file header |


## Solucion
```bash
┌──(kali㉿kali)-[~/Documentos/forensic/c0rrupt]
└─$ wget https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery       
--2024-10-08 12:53:15--  https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 202940 (198K) [application/octet-stream]
Grabando a: «mystery»

mystery           32%[=>      ]  63.72K  4.15KB/s    en 2m 29s  

2024-10-08 12:56:51 (437 B/s) - Error de lectura en el byte 65247/202940 (Error al decodificar el paquete TLS recibido.). Reintentando.

--2024-10-08 12:56:52--  (intento: 2)  https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.
Petición HTTP enviada, esperando respuesta... 206 Partial Content
Longitud: 202940 (198K), quedan 137693 (134K) [application/octet-stream]
Grabando a: «mystery»

mystery          100%[++=====>] 198.18K  18.9KB/s    en 81s     

2024-10-08 12:58:21 (1.67 KB/s) - «mystery» guardado [202940/202940]

                                                                 
┌──(kali㉿kali)-[~/Documentos/forensic/c0rrupt]
└─$ file mystery       
mystery: data
                                                                 
┌──(kali㉿kali)-[~/Documentos/forensic/c0rrupt]
└─$ xxd mystery | head
00000000: 8965 4e34 0d0a b0aa 0000 000d 4322 4452  .eN4........C"DR
00000010: 0000 066a 0000 0447 0802 0000 007c 8bab  ...j...G.....|..
00000020: 7800 0000 0173 5247 4200 aece 1ce9 0000  x....sRGB.......
00000030: 0004 6741 4d41 0000 b18f 0bfc 6105 0000  ..gAMA......a...
00000040: 0009 7048 5973 aa00 1625 0000 1625 0149  ..pHYs...%...%.I
00000050: 5224 f0aa aaff a5ab 4445 5478 5eec bd3f  R$......DETx^..?
00000060: 8e64 cd71 bd2d 8b20 2080 9041 8302 08d0  .d.q.-.  ..A....
00000070: f9ed 40a0 f36e 407b 9023 8f1e d720 8b3e  ..@..n@{.#... .>
00000080: b7c1 0d70 0374 b503 ae41 6bf8 bea8 fbdc  ...p.t...Ak.....
00000090: 3e7d 2a22 336f de5b 55dd 3d3d f920 9188  >}*"3o.[U.==. ..
                                                                 
┌──(kali㉿kali)-[~/Documentos/forensic/c0rrupt]
└─$ hexeditor mystery
                                                                                           
┌──(kali㉿kali)-[~/Documentos/forensic/c0rrupt]
└─$ hexeditor mystery
                                                                                           
┌──(kali㉿kali)-[~/Documentos/forensic/c0rrupt]
└─$ file mystery
mystery: data
                                                                                           
┌──(kali㉿kali)-[~/Documentos/forensic/c0rrupt]
└─$ xxd mystery | head
00000000: 8950 4e47 0d0a b0aa 0000 000d 4948 4452  .PNG........IHDR
00000010: 0000 066a 0000 0447 0802 0000 007c 8bab  ...j...G.....|..
00000020: 7800 0000 0173 5247 4200 aece 1ce9 0000  x....sRGB.......
00000030: 0004 6741 4d41 0000 b18f 0bfc 6105 0000  ..gAMA......a...
00000040: 0009 7048 5973 aa00 1625 0000 1625 0149  ..pHYs...%...%.I
00000050: 5224 f0aa aaff a5ab 4445 5478 5eec bd3f  R$......DETx^..?
00000060: 8e64 cd71 bd2d 8b20 2080 9041 8302 08d0  .d.q.-.  ..A....
00000070: f9ed 40a0 f36e 407b 9023 8f1e d720 8b3e  ..@..n@{.#... .>
00000080: b7c1 0d70 0374 b503 ae41 6bf8 bea8 fbdc  ...p.t...Ak.....
00000090: 3e7d 2a22 336f de5b 55dd 3d3d f920 9188  >}*3o.[U.==. ..
                                                                                           
┌──(kali㉿kali)-[~/Documentos/forensic/c0rrupt]
└─$ file mystery      
mystery: data
                                                                                           
┌──(kali㉿kali)-[~/Documentos/forensic/c0rrupt]
└─$ hexeditor mystery 
                                                                                           
┌──(kali㉿kali)-[~/Documentos/forensic/c0rrupt]
└─$ file mystery     
mystery: PNG image data, 1642 x 1095, 8-bit/color RGB, non-interlaced
                                                                                           
┌──(kali㉿kali)-[~/Documentos/forensic/c0rrupt]
└─$ open mystery     
                                                                                           
┌──(kali㉿kali)-[~/Documentos/forensic/c0rrupt]
└─$ sudo apt install pngcheck
Leyendo lista de paquetes... Hecho
Creando árbol de dependencias... Hecho
Leyendo la información de estado... Hecho
Los paquetes indicados a continuación se instalaron de forma automática y ya no son necesarios.
  bluez-firmware firmware-ath9k-htc firmware-atheros firmware-brcm80211
  firmware-intel-sound firmware-libertas firmware-realtek firmware-sof-signed
  firmware-ti-connectivity firmware-zd1211 kali-linux-firmware
Utilice «sudo apt autoremove» para eliminarlos.
Se instalarán los siguientes paquetes NUEVOS:
  pngcheck
0 actualizados, 1 nuevos se instalarán, 0 para eliminar y 1809 no actualizados.
Se necesita descargar 68.6 kB de archivos.
Se utilizarán 208 kB de espacio de disco adicional después de esta operación.
Des:1 http://kali.download/kali kali-rolling/main amd64 pngcheck amd64 3.0.3-3 [68.6 kB]
Descargados 68.6 kB en 3s (27.2 kB/s) 
Seleccionando el paquete pngcheck previamente no seleccionado.
(Leyendo la base de datos ... 398979 ficheros o directorios instalados actualmente.)
Preparando para desempaquetar .../pngcheck_3.0.3-3_amd64.deb ...
Desempaquetando pngcheck (3.0.3-3) ...
Configurando pngcheck (3.0.3-3) ...
Procesando disparadores para man-db (2.11.2-2) ...
Procesando disparadores para kali-menu (2023.1.7) ...
                                                                                           
┌──(kali㉿kali)-[~/Documentos/forensic/c0rrupt]
└─$ pngcheck -v mystery 
File: mystery (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 2852132389x5669 pixels/meter
  CRC error in chunk pHYs (computed 38d82c82, expected 495224f0)
ERRORS DETECTED in mystery
                                                                                           
┌──(kali㉿kali)-[~/Documentos/forensic/c0rrupt]
└─$ hexeditor mystery        
                                                                                           
┌──(kali㉿kali)-[~/Documentos/forensic/c0rrupt]
└─$ pngcheck -v mystery
File: mystery (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 5669x5669 pixels/meter (144 dpi)
:  invalid chunk length (too large)
ERRORS DETECTED in mystery
                                                                                           
┌──(kali㉿kali)-[~/Documentos/forensic/c0rrupt]
└─$ hexeditor mystery        
                                                                                           
┌──(kali㉿kali)-[~/Documentos/forensic/c0rrupt]
└─$ pngcheck -v mystery
File: mystery (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 5669x5669 pixels/meter (144 dpi)
:  invalid chunk length (too large)
ERRORS DETECTED in mystery
                                                                                           
┌──(kali㉿kali)-[~/Documentos/forensic/c0rrupt]
└─$ hexeditor mystery  
                                                                                           
┌──(kali㉿kali)-[~/Documentos/forensic/c0rrupt]
└─$ pngcheck -v mystery
File: mystery (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 5669x5669 pixels/meter (144 dpi)
:  invalid chunk length (too large)
ERRORS DETECTED in mystery
                                                                                           
┌──(kali㉿kali)-[~/Documentos/forensic/c0rrupt]
└─$ hexeditor mystery  
                                                                                           
┌──(kali㉿kali)-[~/Documentos/forensic/c0rrupt]
└─$ pngcheck -v mystery
File: mystery (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 5669x5669 pixels/meter (144 dpi)
  chunk IDAT at offset 0x00057, length 65445
    zlib: deflated, 32K window, fast compression
  chunk IDAT at offset 0x10008, length 65524
  chunk IDAT at offset 0x20008, length 65524
  chunk IDAT at offset 0x30008, length 6304
  chunk IEND at offset 0x318b4, length 0
No errors detected in mystery (9 chunks, 96.3% compression).
                                                                                           
┌──(kali㉿kali)-[~/Documentos/forensic/c0rrupt]
└─$ open mystery
```

## Notas adicionales

## Referencias