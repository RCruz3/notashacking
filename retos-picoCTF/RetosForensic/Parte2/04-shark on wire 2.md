# shark on wire 2

## Objetivo
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recover the flag that was pilfered from the network.

## Pistas

| No. Pista | Pista |
| --------- | ----- |
|           |       |


## Solucion
```bash
┌──(kali㉿kali)-[~/Documentos/forensic/sharkonwire2]
└─$ wget https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap
--2024-10-08 14:39:19--  https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 112318 (110K) [application/octet-stream]
Grabando a: «capture.pcap»

capture.pcap     100%[========>] 109.69K   461KB/s    en 0.2s    

2024-10-08 14:39:22 (461 KB/s) - «capture.pcap» guardado [112318/112318]

                                                                  
┌──(kali㉿kali)-[~/Documentos/forensic/sharkonwire2]
└─$ file capture.pcap
capture.pcap: pcap capture file, microsecond ts (little-endian) - version 2.4 (Ethernet, capture length 262144)
                                                                  
┌──(kali㉿kali)-[~/Documentos/forensic/sharkonwire2]
└─$ wireshark capture.pcap

^C
                                                                  
┌──(kali㉿kali)-[~/Documentos/forensic/sharkonwire2]
└─$ python3 -m pip install scapy
Defaulting to user installation because normal site-packages is not writeable
Requirement already satisfied: scapy in /usr/lib/python3/dist-packages (2.5.0)
                                                                  
┌──(kali㉿kali)-[~/Documentos/forensic/sharkonwire2]
└─$ nano exp.py
                                                                  
┌──(kali㉿kali)-[~/Documentos/forensic/sharkonwire2]
└─$ nano exp.py
                                                                  
┌──(kali㉿kali)-[~/Documentos/forensic/sharkonwire2]
└─$ python3 exp.py
picoCTF{p1LLf3r3d_data_v1a_st3g0}
```

## Notas adicionales
El codigo de exp.py es el siguiente:
```bash
from scapy.all import *

packets = rdpcap('capture.pcap')
flag = ''

for p in packets:
        if UDP in p and p[UDP].dport == 22:
                if p[UDP].sport > 5000:
                        flag += chr(p[UDP].sport - 5000)
print(flag)
```

## Referencias