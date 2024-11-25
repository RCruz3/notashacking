# timer

## Objetivo
You will find the flag after analysing this apkDownload [here](https://artifacts.picoctf.net/c/449/timer.apk).

## Pistas

| No. Pista | Pista |
| --------- | ----- |
|           |       |


## Solucion
```bash
┌──(kali㉿kali)-[~/Documentos/reversing]
└─$ sudo apt install jadx
Leyendo lista de paquetes... Hecho
Creando árbol de dependencias... Hecho
Leyendo la información de estado... Hecho
Los paquetes indicados a continuación se instalaron de forma automática y ya no son necesarios.
  bluez-firmware firmware-ath9k-htc firmware-atheros firmware-brcm80211
  firmware-intel-sound firmware-libertas firmware-realtek firmware-sof-signed
  firmware-ti-connectivity firmware-zd1211 kali-linux-firmware
Utilice «sudo apt autoremove» para eliminarlos.
Se instalarán los siguientes paquetes NUEVOS:
  jadx
0 actualizados, 1 nuevos se instalarán, 0 para eliminar y 2100 no actualizados.
Se necesita descargar 104 MB de archivos.
Se utilizarán 115 MB de espacio de disco adicional después de esta operación.
Des:1 http://mirrors.ocf.berkeley.edu/kali kali-rolling/main amd64 jadx all 1.5.0-0kali2 [104 MB]
Ign:1 http://mirrors.ocf.berkeley.edu/kali kali-rolling/main amd64 jadx all 1.5.0-0kali2    
Des:1 http://mirrors.ocf.berkeley.edu/kali kali-rolling/main amd64 jadx all 1.5.0-0kali2 [104 MB]
Descargados 72.4 MB en 8min 8s (149 kB/s)                                                   
Seleccionando el paquete jadx previamente no seleccionado.
(Leyendo la base de datos ... 402016 ficheros o directorios instalados actualmente.)
Preparando para desempaquetar .../jadx_1.5.0-0kali2_all.deb ...
Desempaquetando jadx (1.5.0-0kali2) ...
Configurando jadx (1.5.0-0kali2) ...
Procesando disparadores para kali-menu (2023.1.7) ...
                                                                                             
┌──(kali㉿kali)-[~/Documentos/reversing]
└─$ sudo mv timer.apk /usr/share/jadx/bin/
[sudo] contraseña para kali: 
                                                                                             
┌──(kali㉿kali)-[~/Documentos/reversing]
└─$ cd /usr/share/jadx/bin
                                                                                             
┌──(kali㉿kali)-[/usr/share/jadx/bin]
└─$ sudo jadx -d out timer.apk && cd out/resources
INFO  - loading ...
INFO  - processing ...
ERROR - finished with errors, count: 3                       
                                                                                             
┌──(kali㉿kali)-[/usr/…/jadx/bin/out/resources]
└─$ cat AndroidManifest.xml | grep pico
    android:versionName="picoCTF{t1m3r_r3v3rs3d_succ355fully_17496}"

```

## Notas adicionales

## Referencias