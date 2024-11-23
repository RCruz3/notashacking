# Transformation

## Objetivo

I wonder what this really is... [enc](https://mercury.picoctf.net/static/a757282979af14ab5ed74f0ed5e2ca95/enc) `''.join([chr((ord(flag[i]) << 8) + ord(flag[i + 1])) for i in range(0, len(flag), 2)])`
## Pistas

| No. Pista | Pista                             |
| --------- | --------------------------------- |
| 1         | You may find some decoders online |

## Solucion
```bash
┌──(kali㉿kali)-[~/Documentos/reversing]
└─$ cat enc     
灩捯䍔䙻ㄶ形楴獟楮獴㌴摟潦弸彤㔲挶戹㍽                                                                                   
┌──(kali㉿kali)-[~/Documentos/reversing]
└─$ python 
Python 3.11.4 (main, Jun  7 2023, 10:13:09) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> enc= open("enc").read()
>>> for c in enc:
...     print(hex(ord(c)).lstrip("0x"),end='')
... 
7069636f4354467b31365f626974735f696e73743334645f6f665f385f64353263366239337d>>> 
picoCTF{16_bits_inst34d_of_8_d52c6b93}
```

## Notas adicionales

## Referencias