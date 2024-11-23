# PBit-O-Asm-2

## Objetivo
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`. Download the assembly dump [here](https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt).
## Pistas

| No. Pista | Pista                                                                           |
| --------- | ------------------------------------------------------------------------------- |
| 1         | PTR's or 'pointers', reference a location in memory where values can be stored. |


## Solucion
```bash
┌──(kali㉿kali)-[~/Documentos/reversing]
└─$ wget https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt
--2024-06-09 00:34:04--  https://artifacts.picoctf.net/c/510/disassembler-dump0_b.
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.225.62, 3.161.21.225.3, ...
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[3.161.225.62]:443... 
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 270 [application/octet-stream]
Grabando a: «disassembler-dump0_b.txt»

disassembler-dump0_b.tx 100%[============================>]     270  --.-KB/s    e

2024-06-09 00:34:17 (141 MB/s) - «disassembler-dump0_b.txt» guardado [270/270]

                                                                                  
┌──(kali㉿kali)-[~/Documentos/reversing]
└─$ cat disassembler-dump0_b.txt                                     
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a
<+22>:    mov    eax,DWORD PTR [rbp-0x4]
<+25>:    pop    rbp
<+26>:    ret
                                                                                  
┌──(kali㉿kali)-[~/Documentos/reversing]
└─$ python3                                                          
Python 3.11.4 (main, Jun  7 2023, 10:13:09) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> print(int("0x9fe1a",16))
654874

picoCTF{654874}
```

## Notas adicionales

## Referencias