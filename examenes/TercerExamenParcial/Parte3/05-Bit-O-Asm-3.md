# Bit-O-Asm-3

## Objetivo
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`. Download the assembly dump [here](https://artifacts.picoctf.net/c/530/disassembler-dump0_c.txt).
## Pistas

| No. Pista | Pista                                                  |
| --------- | ------------------------------------------------------ |
| 1         | Not everything in this disassembly listing is optimal. |


## Solucion
```bash
┌──(kali㉿kali)-[~/Documentos/reversing]
└─$ wget https://artifacts.picoctf.net/c/530/disassembler-dump0_c.txt
--2024-06-09 00:37:10--  https://artifacts.picoctf.net/c/530/disassembler-dump0_c.txt
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.225.3, 3.161.225.11, 3.161.225.62, ...
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[3.161.225.3]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 461 [application/octet-stream]
Grabando a: «disassembler-dump0_c.txt»

disassembler-dump0_c 100%[====================>]     461  --.-KB/s    en 0s      

2024-06-09 00:37:15 (250 MB/s) - «disassembler-dump0_c.txt» guardado [461/461]

                                                                                  
┌──(kali㉿kali)-[~/Documentos/reversing]
└─$ cat disassembler-dump0_c.txt                                     
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0xc],0x9fe1a
<+22>:    mov    DWORD PTR [rbp-0x8],0x4
<+29>:    mov    eax,DWORD PTR [rbp-0xc]
<+32>:    imul   eax,DWORD PTR [rbp-0x8]
<+36>:    add    eax,0x1f5
<+41>:    mov    DWORD PTR [rbp-0x4],eax
<+44>:    mov    eax,DWORD PTR [rbp-0x4]
<+47>:    pop    rbp
<+48>:    ret
                                                                                  
┌──(kali㉿kali)-[~/Documentos/reversing]
└─$ python3 
Python 3.11.4 (main, Jun  7 2023, 10:13:09) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> print(int((0x9fe1a * 0x4) + 0x1f5))
2619997

picoCTF{2619997}
```

## Notas adicionales

## Referencias