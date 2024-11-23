# miniRSA

## Objetivo
Let's decrypt this: [ciphertext](https://jupiter.challenges.picoctf.org/static/ee7e2388b45f521b285334abb5a63771/ciphertext)? Something seems a bit small.

## Pistas

| No. Pistas | Pista                                                                                |
| ---------- | ------------------------------------------------------------------------------------ |
| 1          | RSA [tutorial](https://en.wikipedia.org/wiki/RSA_(cryptosystem))                     |
| 2          | How could having too small an e affect the security of this 2048 bit key?            |
| 3          | Make sure you don't lose precision, the numbers are pretty big (besides the e value) |

## Solucion
```bash
┌──(kali㉿kali)-[~/Documentos/crypto/miniRSA]
└─$ wget https://jupiter.challenges.picoctf.org/static/ee7e2388b45f521b285334abb5a63771/ciphertext
--2024-05-16 17:13:28--  https://jupiter.challenges.picoctf.org/static/ee7e2388b45f521b285334abb5a63771/ciphertext
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 884 [application/octet-stream]
Grabando a: «ciphertext»

ciphertext           100%[====================>]     884  --.-KB/s    en 0s      

2024-05-16 17:13:31 (13.2 MB/s) - «ciphertext» guardado [884/884]

                                                                                  
┌──(kali㉿kali)-[~/Documentos/crypto/miniRSA]
└─$ ls
ciphertext
                                                                                  
┌──(kali㉿kali)-[~/Documentos/crypto/miniRSA]
└─$ file ciphertext
ciphertext: ASCII text, with very long lines (620)
                                                                                  
┌──(kali㉿kali)-[~/Documentos/crypto/miniRSA]
└─$ cat ciphertext     

N: 29331922499794985782735976045591164936683059380558950386560160105740343201513369939006307531165922708949619162698623675349030430859547825708994708321803705309459438099340427770580064400911431856656901982789948285309956111848686906152664473350940486507451771223435835260168971210087470894448460745593956840586530527915802541450092946574694809584880896601317519794442862977471129319781313161842056501715040555964011899589002863730868679527184420789010551475067862907739054966183120621407246398518098981106431219207697870293412176440482900183550467375190239898455201170831410460483829448603477361305838743852756938687673
e: 3

ciphertext (c): 2205316413931134031074603746928247799030155221252519872649649212867614751848436763801274360463406171277838056821437115883619169702963504606017565783537203207707757768473109845162808575425972525116337319108047893250549462147185741761825125 
                                                                                  
┌──(kali㉿kali)-[~/Documentos/crypto/miniRSA]
└─$ sudo python3 -m pip install gmpy2
[sudo] contraseña para kali: 
Collecting gmpy2
  Downloading gmpy2-2.1.5-cp311-cp311-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (1.8 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 1.8/1.8 MB 1.5 MB/s eta 0:00:00
Installing collected packages: gmpy2
Successfully installed gmpy2-2.1.5
WARNING: Running pip as the 'root' user can result in broken permissions and conflicting behaviour with the system package manager. It is recommended to use a virtual environment instead: https://pip.pypa.io/warnings/venv                         
                                                                                  
┌──(kali㉿kali)-[~/Documentos/crypto/miniRSA]
└─$ sudo python3 -m pip install pycryptodome
Collecting pycryptodome
  Downloading pycryptodome-3.20.0-cp35-abi3-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (2.1 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 2.1/2.1 MB 1.5 MB/s eta 0:00:00
Installing collected packages: pycryptodome
Successfully installed pycryptodome-3.20.0
WARNING: Running pip as the 'root' user can result in broken permissions and conflicting behaviour with the system package manager. It is recommended to use a virtual environment instead: https://pip.pypa.io/warnings/venv                         
                                                                                  
┌──(kali㉿kali)-[~/Documentos/crypto/miniRSA]
└─$ python3
Python 3.11.4 (main, Jun  7 2023, 10:13:09) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> from gmpy2 import *
>>> from Crypto.Util.number import long_to_bytes
>>> gmpy2.get_context().precision=2048
>>> e = 3
>>> c = 2205316413931134031074603746928247799030155221252519872649649212867614751848436763801274360463406171277838056821437115883619169702963504606017565783537203207707757768473109845162808575425972525116337319108047893250549462147185741761825125>>> root, exact = iroot(c, e)
>>> root
mpz(13016382529449106065894479374027604750406953699090365388202874238148389207291005)
>>> print(long_to_bytes(root))
b'picoCTF{n33d_a_lArg3r_e_606ce004}'

```

## Notas adicionales

## Referencias