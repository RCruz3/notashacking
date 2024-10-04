# shark on wire 1
## Objetivo
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap). Recover the flag.

## Pistas

| No. Pista | Pista                           |
| --------- | ------------------------------- |
| 1         | Try using a tool like Wireshark |
| 2         | What are streams?               |


## Solucion
```bash
┌──(kali㉿kali)-[~/Documentos/forensic]
└─$ wget https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap
--2024-03-15 01:18:33--  https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 239455 (234K) [application/octet-stream]
Grabando a: «capture.pcap»

capture.pcap             100%[================================>] 233.84K  1.09MB/s    en 0.2s    

2024-03-15 01:18:34 (1.09 MB/s) - «capture.pcap» guardado [239455/239455]

                                                                                                  
┌──(kali㉿kali)-[~/Documentos/forensic]
└─$ ls
capture.pcap  flag.png  garden.jpg
                                                                                                  
┌──(kali㉿kali)-[~/Documentos/forensic]
└─$ file capture.pcap 
capture.pcap: pcap capture file, microsecond ts (little-endian) - version 2.4 (Ethernet, capture length 262144)
```

## Notas adicionales
* Uso de wireshark para resolver el reto

## Referencias