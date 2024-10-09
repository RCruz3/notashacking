# WhitePages

## Objetivo
I stopped using YellowPages and moved onto WhitePages... but [the page they gave me](https://jupiter.challenges.picoctf.org/static/fa4a277cfa846e07a5981d8a19288a2e/whitepages.txt) is all blank!

## Pistas

| No. Pista | Pista |
| --------- | ----- |
|           |       |


## Solucion
```bash
┌──(kali㉿kali)-[~/Documentos/forensic/WhitePages]
└─$ wget https://jupiter.challenges.picoctf.org/static/fa4a277cfa846e07a5981d8a19288a2e/whitepages.txt
--2024-10-08 12:30:07--  https://jupiter.challenges.picoctf.org/static/fa4a277cfa846e07a5981d8a19288a2e/whitepages.txt
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 2982 (2.9K) [application/octet-stream]
Grabando a: «whitepages.txt»

whitepages.txt   100%[=======>]   2.91K  --.-KB/s    en 0s      

2024-10-08 12:30:09 (63.4 MB/s) - «whitepages.txt» guardado [2982/2982]

                                                                 
┌──(kali㉿kali)-[~/Documentos/forensic/WhitePages]
└─$ cat whitepages.txt
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 
┌──(kali㉿kali)-[~/Documentos/forensic/WhitePages]
└─$ ls -la
total 12
drwxr-xr-x 2 kali kali 4096 mar 27 12:30 .
drwxr-xr-x 4 kali kali 4096 mar 27 12:29 ..
-rw-r--r-- 1 kali kali 2982 oct 26  2020 whitepages.txt
                                                                 
┌──(kali㉿kali)-[~/Documentos/forensic/WhitePages]
└─$ wc whitepages.txt 
   0    0 2982 whitepages.txt
                                                                 
┌──(kali㉿kali)-[~/Documentos/forensic/WhitePages]
└─$ file whitepages.txt 
whitepages.txt: Unicode text, UTF-8 text, with very long lines (1376), with no line terminators
                                                                 
┌──(kali㉿kali)-[~/Documentos/forensic/WhitePages]
└─$ xxd whitepages.txt | head
00000000: e280 83e2 8083 e280 83e2 8083 20e2 8083  ............ ...
00000010: 20e2 8083 e280 83e2 8083 e280 83e2 8083   ...............
00000020: 20e2 8083 e280 8320 e280 83e2 8083 e280   ...... ........
00000030: 83e2 8083 20e2 8083 e280 8320 e280 8320  .... ...... ... 
00000040: 2020 e280 83e2 8083 e280 83e2 8083 e280    ..............
00000050: 8320 20e2 8083 20e2 8083 e280 8320 e280  .  ... ...... ..
00000060: 8320 20e2 8083 e280 83e2 8083 2020 e280  .  .........  ..
00000070: 8320 20e2 8083 2020 2020 e280 8320 e280  .  ...    ... ..
00000080: 83e2 8083 e280 83e2 8083 2020 e280 8320  ..........  ... 
00000090: e280 8320 e280 8320 e280 83e2 8083 e280  ... ... ........
                                                                 
┌──(kali㉿kali)-[~/Documentos/forensic/WhitePages]
└─$ python3 -m pip install pwntools
Defaulting to user installation because normal site-packages is not writeable
Collecting pwntools
  Downloading pwntools-4.12.0-py2.py3-none-any.whl (11.8 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━ 11.8/11.8 MB 624.3 kB/s eta 0:00:00
Requirement already satisfied: paramiko>=1.15.2 in /usr/lib/python3/dist-packages (from pwntools) (2.12.0)
Requirement already satisfied: mako>=1.0.0 in /usr/lib/python3/dist-packages (from pwntools) (1.2.4.dev0)
Collecting capstone>=3.0.5rc2
  Downloading capstone-5.0.1-py3-none-manylinux1_x86_64.manylinux_2_5_x86_64.whl (2.9 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━ 2.9/2.9 MB 354.7 kB/s eta 0:00:00
Collecting ropgadget>=5.3
  Downloading ROPGadget-7.4-py3-none-any.whl (32 kB)
Requirement already satisfied: pyserial>=2.7 in /usr/lib/python3/dist-packages (from pwntools) (3.5)
Requirement already satisfied: requests>=2.0 in /usr/lib/python3/dist-packages (from pwntools) (2.28.1)
Requirement already satisfied: pip>=6.0.8 in /usr/lib/python3/dist-packages (from pwntools) (23.0.1)
Requirement already satisfied: pygments>=2.0 in /usr/lib/python3/dist-packages (from pwntools) (2.14.0)
Requirement already satisfied: pysocks in /usr/lib/python3/dist-packages (from pwntools) (1.7.1)
Requirement already satisfied: python-dateutil in /usr/lib/python3/dist-packages (from pwntools) (2.8.2)
Requirement already satisfied: packaging in /usr/lib/python3/dist-packages (from pwntools) (23.0)
Requirement already satisfied: psutil>=3.3.0 in /usr/lib/python3/dist-packages (from pwntools) (5.9.4)
Collecting intervaltree>=3.0
  Downloading intervaltree-3.1.0.tar.gz (32 kB)
  Preparing metadata (setup.py) ... done
Requirement already satisfied: sortedcontainers in /usr/lib/python3/dist-packages (from pwntools) (2.4.0)
Collecting unicorn>=1.0.2rc1
  Downloading unicorn-2.0.1.post1-py2.py3-none-manylinux1_x86_64.manylinux_2_17_x86_64.manylinux2014_x86_64.whl (16.1 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━ 16.1/16.1 MB 457.9 kB/s eta 0:00:00
Requirement already satisfied: six>=1.12.0 in /usr/lib/python3/dist-packages (from pwntools) (1.16.0)
Collecting rpyc
  Downloading rpyc-6.0.0-py3-none-any.whl (74 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━ 74.5/74.5 kB 397.5 kB/s eta 0:00:00
Collecting colored-traceback
  Downloading colored-traceback-0.3.0.tar.gz (3.8 kB)
  Preparing metadata (setup.py) ... done
Collecting zstandard
  Downloading zstandard-0.22.0-cp311-cp311-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (5.4 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━ 5.4/5.4 MB 507.4 kB/s eta 0:00:00
Collecting pyelftools>=0.24
  Downloading pyelftools-0.31-py3-none-any.whl (180 kB)
     ━━━━━━━━━━━━━━━━━━━━━━ 180.5/180.5 kB 668.9 kB/s eta 0:00:00
Collecting unix-ar
  Downloading unix_ar-0.2.1-py2.py3-none-any.whl (6.5 kB)
Collecting plumbum
  Downloading plumbum-1.8.2-py3-none-any.whl (127 kB)
     ━━━━━━━━━━━━━━━━━━━━━━ 127.0/127.0 kB 485.6 kB/s eta 0:00:00
Building wheels for collected packages: intervaltree, colored-traceback
  Building wheel for intervaltree (setup.py) ... done
  Created wheel for intervaltree: filename=intervaltree-3.1.0-py2.py3-none-any.whl size=26098 sha256=6858b627ed058346f58c74f1a804e8903a54d5dfcdd045220d5a03cb5b1acb49
  Stored in directory: /home/kali/.cache/pip/wheels/31/d7/d9/eec6891f78cac19a693bd40ecb8365d2f4613318c145ec9816
  Building wheel for colored-traceback (setup.py) ... done
  Created wheel for colored-traceback: filename=colored_traceback-0.3.0-py3-none-any.whl size=4607 sha256=07386babc25e50a2d63b6d2d82be8963dad1151e2767422b2da6da0854bd2519
  Stored in directory: /home/kali/.cache/pip/wheels/45/a9/5f/635d7d8d70eb182fd22f2b0bebce713206e172769bea9f106a
Successfully built intervaltree colored-traceback
Installing collected packages: unicorn, pyelftools, zstandard, unix-ar, plumbum, intervaltree, colored-traceback, capstone, rpyc, ropgadget, pwntools
  WARNING: The scripts rpyc_classic, rpyc_classic.py, rpyc_registry and rpyc_registry.py are installed in '/home/kali/.local/bin' which is not on PATH.                                            
  Consider adding this directory to PATH or, if you prefer to suppress this warning, use --no-warn-script-location.               
  WARNING: The scripts asm, checksec, common, constgrep, cyclic, debug, disablenx, disasm, elfdiff, elfpatch, errno, hex, libcdb, main, phd, pwn, pwnstrip, scramble, shellcraft, template, unhex, update and version are installed in '/home/kali/.local/bin' which is not on PATH.                                                 
  Consider adding this directory to PATH or, if you prefer to suppress this warning, use --no-warn-script-location.               
Successfully installed capstone-5.0.1 colored-traceback-0.3.0 intervaltree-3.1.0 plumbum-1.8.2 pwntools-4.12.0 pyelftools-0.31 ropgadget-7.4 rpyc-6.0.0 unicorn-2.0.1.post1 unix-ar-0.2.1 zstandard-0.22.0
                                                                 
┌──(kali㉿kali)-[~/Documentos/forensic/WhitePages]
└─$ nano exp.py  
                                                                 
┌──(kali㉿kali)-[~/Documentos/forensic/WhitePages]
└─$ python exp.py
b'\n\t\tpicoCTF\n\n\t\tSEE PUBLIC RECORDS & BACKGROUND REPORT\n\t\t5000 Forbes Ave, Pittsburgh, PA 15213\n\t\tpicoCTF{not_all_spaces_are_created_equal_3e2423081df9adab2a9d96afda4cfad6}\n\t\t'
```

## Notas adicionales
el codigo de exp.py es el siguiente:
```bash
from pwn import *

file = open('whitepages.txt', 'rb')
data = bytearray(file.read())
data = data.replace(b'\xe2\x80\x83', b'0')
data = data.replace(b'\x20', b'1')
data = data.decode('ascii')
data = unbits(data)
print(data)
```

## Referencias