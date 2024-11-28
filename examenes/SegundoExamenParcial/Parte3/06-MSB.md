# MSB

## Objetivo
This image passes LSB statistical analysis, but we can't help but think there must be something to the visual artifacts present in this image...Download the image [here](https://artifacts.picoctf.net/c/304/Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada.flag.png)

## Pistas

| No. Pista | Pista |
| --------- | ----- |
|           |       |


## Solucion
```bash
┌──(kali㉿kali)-[~/Documents/parcial2]
└─$ wget https://artifacts.picoctf.net/c/304/Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada.flag.png
--2024-11-28 08:47:06--  https://artifacts.picoctf.net/c/304/Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada.flag.png
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.225.222.120, 13.225.222.28, 13.225.222.125, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.225.222.120|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 3354311 (3.2M) [application/octet-stream]
Saving to: ‘Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada.flag.png’

Ninja-and-Prin 100%[====>]   3.20M  2.01MB/s    in 1.6s    

2024-11-28 08:47:10 (2.01 MB/s) - ‘Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada.flag.png’ saved [3354311/3354311]

                                                            
┌──(kali㉿kali)-[~/Documents/parcial2]
└─$ wget https://raw.githubusercontent.com/Pulho/sigBits/master/sigBits.py
--2024-11-28 08:49:13--  https://raw.githubusercontent.com/Pulho/sigBits/master/sigBits.py
Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 185.199.108.133, 185.199.109.133, 185.199.110.133, ...
Connecting to raw.githubusercontent.com (raw.githubusercontent.com)|185.199.108.133|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 7008 (6.8K) [text/plain]
Saving to: ‘sigBits.py’

sigBits.py     100%[====>]   6.84K  --.-KB/s    in 0.01s   

2024-11-28 08:49:13 (570 KB/s) - ‘sigBits.py’ saved [7008/7008]

                                                            
┌──(kali㉿kali)-[~/Documents/parcial2]
└─$ python3 sigBits.py -t=msb Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada.flag.png
Done, check the output file!
                                                            
┌──(kali㉿kali)-[~/Documents/parcial2]
└─$ ls
capture.flag.pcap
dump.pcap
file.des3
file.txt
flag
flag.zip
index.html
Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada.flag.png
outputSB.txt
sigBits.py
                                                            
┌──(kali㉿kali)-[~/Documents/parcial2]
└─$ cat outputSB.txt | grep -o -E "picoCTF.{0,50}"
picoCTF{15_y0ur_que57_qu1x071c_0r_h3r01c_ee3cb4d8}"Thou h
```

## Notas adicionales

## Referencias