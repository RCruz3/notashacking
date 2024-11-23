# Bit-O-Asm-1

## Objetivo
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`. Download the assembly dump [here](https://artifacts.picoctf.net/c/509/disassembler-dump0_a.txt).
## Pistas

| No. Pista | Pista                                                                                                                                                     |
| --------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1         | As with most assembly, there is a lot of noise in the instruction dump. Find the one line that pertains to this question and don't second guess yourself! |


## Solucion
```bash
┌──(kali㉿kali)-[~/Documentos/reversing]
└─$ wget https://artifacts.picoctf.net/c/509/disassembler-dump0_a.txt
--2024-06-09 00:31:41--  https://artifacts.picoctf.net/c/509/disassembler-dump0_a.txt
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.225.11, 3.161.225.60, 3.161.225.3, ...
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[3.161.225.11]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 209 [application/octet-stream]
Grabando a: «disassembler-dump0_a.txt»

disassembler-dump0_a.tx 100%[============================>]     209  --.-KB/s    en 0s      

2024-06-09 00:31:51 (110 MB/s) - «disassembler-dump0_a.txt» guardado [209/209]

                                                                                             
┌──(kali㉿kali)-[~/Documentos/reversing]
└─$ cat disassembler-dump0_a.txt 
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x4],edi
<+11>:    mov    QWORD PTR [rbp-0x10],rsi
<+15>:    mov    eax,0x30
<+20>:    pop    rbp
<+21>:    ret
                                                                                             
┌──(kali㉿kali)-[~/Documentos/reversing]
└─$ python3                                                      
Python 3.11.4 (main, Jun  7 2023, 10:13:09) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> print(int("0x30", 16))
48

picoCTF{48}
```

## Notas adicionales

## Referencias