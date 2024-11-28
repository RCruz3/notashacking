# Eavesdrop

## Objetivo
Download this packet capture and find the flag.

- [Download packet capture](https://artifacts.picoctf.net/c/133/capture.flag.pcap)

## Pistas

| No. Pista | Pista |
| --------- | ----- |
|           |       |


## Solucion
```bash
┌──(kali㉿kali)-[~/Documents/parcial2]
└─$ wireshark capture.flag.pcap 
exit    
^C
                                                            
┌──(kali㉿kali)-[~/Documents/parcial2]
└─$ ls                         
capture.flag.pcap  file.des3  index.html
                                                            
┌──(kali㉿kali)-[~/Documents/parcial2]
└─$ openssl des3 -d -salt -in file.des3 -out file.txt -k supersecretpassword123
*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
                                                            
┌──(kali㉿kali)-[~/Documents/parcial2]
└─$ find file.txt                  
file.txt
                                                            
┌──(kali㉿kali)-[~/Documents/parcial2]
└─$ cat file.txt         
picoCTF{nc_73115_411_5786acc3} 
```

## Notas adicionales

## Referencias