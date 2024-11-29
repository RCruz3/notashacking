# reverse_cipher

## Objetivo
We have recovered a [binary](https://jupiter.challenges.picoctf.org/static/48babf8f8c4c6b8baf336680ea5b9ddf/rev) and a [text file](https://jupiter.challenges.picoctf.org/static/48babf8f8c4c6b8baf336680ea5b9ddf/rev_this). Can you reverse the flag.

## Pistas

| No. Pista | Pista                                                         |
| --------- | ------------------------------------------------------------- |
| 1         | objdump and Gihdra are some tools that could assist with this |


## Solucion
```bash
┌──(kali㉿kali)-[~/Documents/reversing]
└─$ cat rev_this        
picoCTF{w1{1wq8/7376j.:}                                                                       
┌──(kali㉿kali)-[~/Documents/reversing]
└─$ 
                                                                       
┌──(kali㉿kali)-[~/Documents/reversing]
└─$ nano solucion.py  
                                                                       
┌──(kali㉿kali)-[~/Documents/reversing]
└─$ python3 solucion.py
picoCTF{r3v3rs312528e05}                                                                       
┌──(kali㉿kali)-[~/Documents/reversing]
└─$ cat rev_this        
picoCTF{w1{1wq8/7376j.:}
```
Codigo .py
```
import os
import mmap

def memory_map(filename, access=mmap.ACCESS_READ):
    size = os.path.getsize(filename)
    fd = os.open(filename, os.O_RDONLY)
    return mmap.mmap(fd, size, access=access)

with memory_map("rev_this") as bin_file:
    for i in range(8):
        print(chr(bin_file[i]), end = '')
    for i in range(8, 23):
        if (i & 1) == 0:
            print(chr(bin_file[i] - 5), end = '')
        else:
            print(chr(bin_file[i] + 2), end = '')
    print (chr(bin_file[23]))
```

## Notas adicionales

## Referencias