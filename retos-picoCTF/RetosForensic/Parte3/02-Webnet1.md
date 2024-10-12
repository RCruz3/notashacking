# Webnet1

## Objetivo
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key). Recover the flag.

## Pistas

| No. Pista | Pista                               |
| --------- | ----------------------------------- |
| 1         | Try using a tool like Wireshark.    |
| 2         | How can you decrypt the TLS stream? |


## Solucion
```bash
┌──(kali㉿kali)-[~/Documentos/forensic/webnet1]
└─$ wget https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap
--2024-10-11 17:23:38--  https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 92525 (90K) [application/octet-stream]
Grabando a: «capture.pcap»

capture.pcap     100%[========>]  90.36K  --.-KB/s    en 0.1s    

2024-10-11 17:23:41 (620 KB/s) - «capture.pcap» guardado [92525/92525]

                                                                  
┌──(kali㉿kali)-[~/Documentos/forensic/webnet1]
└─$ wget https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key
--2024-10-11 17:24:18--  https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 1704 (1.7K) [application/octet-stream]
Grabando a: «picopico.key»

picopico.key     100%[========>]   1.66K  --.-KB/s    en 0s      

2024-10-11 17:24:19 (38.2 MB/s) - «picopico.key» guardado [1704/1704]

                                                                  
┌──(kali㉿kali)-[~/Documentos/forensic/webnet1]
└─$ ls
capture.pcap  picopico.key
                                                                  
┌──(kali㉿kali)-[~/Documentos/forensic/webnet1]
└─$ wireshark capture.pcap
 ** (wireshark:420636) 17:27:51.331064 [GUI WARNING] -- FIX Add drag reordering to UAT dialog

(wireshark:420636): GLib-GIO-CRITICAL **: 17:29:08.622: GFileInfo created without standard::is-hidden

(wireshark:420636): GLib-GIO-CRITICAL **: 17:29:08.622: file ../../../gio/gfileinfo.c: line 1633 (g_file_info_get_is_hidden): should not be reached

(wireshark:420636): GLib-GIO-CRITICAL **: 17:29:08.622: GFileInfo created without standard::is-backup

(wireshark:420636): GLib-GIO-CRITICAL **: 17:29:08.622: file ../../../gio/gfileinfo.c: line 1655 (g_file_info_get_is_backup): should not be reached

(wireshark:420636): GLib-GIO-CRITICAL **: 17:29:08.622: GFileInfo created without standard::is-hidden

(wireshark:420636): GLib-GIO-CRITICAL **: 17:29:08.622: file ../../../gio/gfileinfo.c: line 1633 (g_file_info_get_is_hidden): should not be reached

(wireshark:420636): GLib-GIO-CRITICAL **: 17:29:08.622: GFileInfo created without standard::is-backup

(wireshark:420636): GLib-GIO-CRITICAL **: 17:29:08.622: file ../../../gio/gfileinfo.c: line 1655 (g_file_info_get_is_backup): should not be reached

(wireshark:420636): GLib-GIO-CRITICAL **: 17:29:12.765: GFileInfo created without standard::is-hidden

(wireshark:420636): GLib-GIO-CRITICAL **: 17:29:12.765: file ../../../gio/gfileinfo.c: line 1633 (g_file_info_get_is_hidden): should not be reached

(wireshark:420636): GLib-GIO-CRITICAL **: 17:29:12.765: GFileInfo created without standard::is-backup

(wireshark:420636): GLib-GIO-CRITICAL **: 17:29:12.765: file ../../../gio/gfileinfo.c: line 1655 (g_file_info_get_is_backup): should not be reached

(wireshark:420636): GLib-GIO-CRITICAL **: 17:29:12.766: GFileInfo created without standard::is-hidden

(wireshark:420636): GLib-GIO-CRITICAL **: 17:29:12.766: file ../../../gio/gfileinfo.c: line 1633 (g_file_info_get_is_hidden): should not be reached

(wireshark:420636): GLib-GIO-CRITICAL **: 17:29:12.766: GFileInfo created without standard::is-backup

(wireshark:420636): GLib-GIO-CRITICAL **: 17:29:12.767: file ../../../gio/gfileinfo.c: line 1655 (g_file_info_get_is_backup): should not be reached
^C
                                                                  
┌──(kali㉿kali)-[~/Documentos/forensic/webnet1]
└─$ ls
capture.pcap  picopico.key  vulture.jpg
                                                                  
┌──(kali㉿kali)-[~/Documentos/forensic/webnet1]
└─$ strings vulture.jpg -n15  
picoCTF{honey.roasted.peanuts}
 )/'%'/9339GDG]]}
 )/'%'/9339GDG]]}
%&'()*456789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz
&'()*56789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz

```

## Notas adicionales
* Mismo proceso de agregar la llave
* Exportar el objeto de la imagen para hacerle un strings

## Referencias