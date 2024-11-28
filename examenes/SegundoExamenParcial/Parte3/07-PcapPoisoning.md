# PcapPoisoning

## Objetivo
How about some hide and seek heh?Download this [file](https://artifacts.picoctf.net/c/373/trace.pcap) and find the flag.

## Pistas

| No. Pista | Pista |
| --------- | ----- |
|           |       |


## Solucion
```bash
┌──(kali㉿kali)-[~/Documents/parcial2]
└─$ wireshark trace.pcap                               
^C
                                                            
┌──(kali㉿kali)-[~/Documents/parcial2]
└─$ strings trace.pcap | grep -E "pico"
picoCTF{P64P_4N4L7S1S_SU55355FUL_4d72dfcc}
```

## Notas adicionales

## Referencias