# Packets Primer

## Objetivo
Download the packet capture file and use packet analysis software to find the flag.

- [Download packet capture](https://artifacts.picoctf.net/c/196/network-dump.flag.pcap)

## Pistas

| No. Pistas | Pista                                                                                                              |
| ---------- | ------------------------------------------------------------------------------------------------------------------ |
| 1          | Wireshark, if you can install and use it, is probably the most beginner friendly packet analysis software product. |

## Solucion
```
La bandera se encontraba al seleccionar el paquete numero 4 y darle en Data y asi podremos ver la bandera:

p i c o C T F { p 4 c k 3 7 _ 5 h 4 r k _ 0 1 b 0 a 0 d 6 }
```

## Notas adicionales

## Referencias