# Mind your Ps and Qs
## Objetivo
In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/51d68e61bb41207a55f24e753f07c5a3/values)
## Pistas

| No.  Pista | Pista                                                               |
| ---------- | ------------------------------------------------------------------- |
| 1          | Bits are expensive, I used only a little bit over 100 to save money |

## Solucion
```bash
┌──(kali㉿kali)-[~/Documentos/crypto/mindyourpsandqs]
└─$ wget https://mercury.picoctf.net/static/51d68e61bb41207a55f24e753f07c5a3/values
--2024-05-16 17:42:52--  https://mercury.picoctf.net/static/51d68e61bb41207a55f24e753f07c5a3/values
Resolviendo mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Conectando con mercury.picoctf.net (mercury.picoctf.net)[18.189.209.142]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 205 [application/octet-stream]
Grabando a: «values»

values               100%[====================>]     205  --.-KB/s    en 0s      

2024-05-16 17:42:55 (143 MB/s) - «values» guardado [205/205]

                                                                                  
┌──(kali㉿kali)-[~/Documentos/crypto/mindyourpsandqs]
└─$ ls
values
                                                                                  
┌──(kali㉿kali)-[~/Documentos/crypto/mindyourpsandqs]
└─$ cat values        
Decrypt my super sick RSA:
c: 62324783949134119159408816513334912534343517300880137691662780895409992760262021
n: 1280678415822214057864524798453297819181910621573945477544758171055968245116423923
e: 65537                                                                                  
┌──(kali㉿kali)-[~/Documentos/crypto/mindyourpsandqs]
└─$ python3
Python 3.11.4 (main, Jun  7 2023, 10:13:09) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> from Crypto.Util.number import long_to_bytes
>>> from Crypto.Util.number import inverse
>>> c = 62324783949134119159408816513334912534343517300880137691662780895409992760262021
>>> e = 65537
>>> p = 1899107986527483535344517113948531328331
>>> q = 674357869540600933870145899564746495319033
>>> n = p * q
>>> n
1280678415822214057864524798453297819181910621573945477544758171055968245116423923
>>> tn = (p-1)*(q-1)
>>> d = inverse(e,tn)
>>> m = pow(c,d,n)
>>> m
13016382529449106065927291425342535437996222135352905256639555654677400177227645
>>> long_to_bytes(m)
b'picoCTF{sma11_N_n0_g0od_05012767}'

```

## Notas adicionales

## Referencias