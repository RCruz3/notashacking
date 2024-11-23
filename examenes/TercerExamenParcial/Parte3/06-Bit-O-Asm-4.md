# Bit-O-Asm-4

## Objetivo
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`. Download the assembly dump [here](https://artifacts.picoctf.net/c/511/disassembler-dump0_d.txt).
## Pistas

| No. Pista | Pista                                                                                                                  |
| --------- | ---------------------------------------------------------------------------------------------------------------------- |
| 1         | Don't tell anyone I told you this, but you can solve this problem without understanding the compare/jump relationship. |
| 2         | Of course, if you're really good, you'll only need one attempt to solve this problem.                                  |


## Solucion
```bash
┌──(kali㉿kali)-[~/Documentos/reversing]
└─$ wget https://artifacts.picoctf.net/c/511/disassembler-dump0_d.txt
--2024-06-09 00:40:06--  https://artifacts.picoctf.net/c/511/disassembler-dump0_d.txt
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.225.60, 3.161.225.11, 3.161.225.62, ...
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[3.161.225.60]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 482 [application/octet-stream]
Grabando a: «disassembler-dump0_d.txt»

disassembler-dump0_d 100%[====================>]     482  --.-KB/s    en 0s      

2024-06-09 00:40:10 (8.46 MB/s) - «disassembler-dump0_d.txt» guardado [482/482]

                                                                                  
┌──(kali㉿kali)-[~/Documentos/reversing]
└─$ cat disassembler-dump0_d.txt
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a
<+22>:    cmp    DWORD PTR [rbp-0x4],0x2710
<+29>:    jle    0x55555555514e <main+37>
<+31>:    sub    DWORD PTR [rbp-0x4],0x65
<+35>:    jmp    0x555555555152 <main+41>
<+37>:    add    DWORD PTR [rbp-0x4],0x65
<+41>:    mov    eax,DWORD PTR [rbp-0x4]
<+44>:    pop    rbp
<+45>:    ret
                                                                                  
┌──(kali㉿kali)-[~/Documentos/reversing]
└─$ python3                                                          
Python 3.11.4 (main, Jun  7 2023, 10:13:09) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> print(int(0x9fe1a - 0x65))
654773

picoCTF{654773}
```

## Notas adicionales

## Referencias