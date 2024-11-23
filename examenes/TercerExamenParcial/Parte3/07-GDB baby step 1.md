# GDB baby step 1

## Objetivo
Can you figure out what is in the `eax` register at the end of the `main` function? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`. Disassemble [this](https://artifacts.picoctf.net/c/512/debugger0_a).
## Pistas

| No. Pista | Pista                                                                      |
| --------- | -------------------------------------------------------------------------- |
| 1         | gdb is a very good debugger to use for this problem and many others!       |
| 2         | `main` is actually a recognized symbol that can be used with gdb commands. |


## Solucion
```bash
┌──(kali㉿kali)-[~/Documentos/reversing]
└─$ wget https://artifacts.picoctf.net/c/512/debugger0_a             
--2024-06-09 00:42:57--  https://artifacts.picoctf.net/c/512/debugger0_a
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.225.62, 3.161.225.11, 3.161.225.3, ...
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[3.161.225.62]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 16472 (16K) [application/octet-stream]
Grabando a: «debugger0_a»

debugger0_a          100%[====================>]  16.09K  25.6KB/s    en 0.6s    

2024-06-09 00:43:16 (25.6 KB/s) - «debugger0_a» guardado [16472/16472]

                                                                                  
┌──(kali㉿kali)-[~/Documentos/reversing]
└─$ file debugger0_a                                    
debugger0_a: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=15a10290db2cd2ec0c123cf80b88ed7d7f5cf9ff, for GNU/Linux 3.2.0, not stripped
                                                                                  
┌──(kali㉿kali)-[~/Documentos/reversing]
└─$ gdb debugger0_a   
GNU gdb (Debian 13.2-1) 13.2
Copyright (C) 2023 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<https://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from debugger0_a...
(No debugging symbols found in debugger0_a)
(gdb) info function
All defined functions:

Non-debugging symbols:
0x0000000000001000  _init
0x0000000000001030  __cxa_finalize@plt
0x0000000000001040  _start
0x0000000000001070  deregister_tm_clones
0x00000000000010a0  register_tm_clones
0x00000000000010e0  __do_global_dtors_aux
0x0000000000001120  frame_dummy
0x0000000000001129  main
0x0000000000001140  __libc_csu_init
0x00000000000011b0  __libc_csu_fini
0x00000000000011b8  _fini
(gdb) disas main
Dump of assembler code for function main:
   0x0000000000001129 <+0>:     endbr64
   0x000000000000112d <+4>:     push   %rbp
   0x000000000000112e <+5>:     mov    %rsp,%rbp
   0x0000000000001131 <+8>:     mov    %edi,-0x4(%rbp)
   0x0000000000001134 <+11>:    mov    %rsi,-0x10(%rbp)
   0x0000000000001138 <+15>:    mov    $0x86342,%eax
   0x000000000000113d <+20>:    pop    %rbp
   0x000000000000113e <+21>:    ret
End of assembler dump.
┌──(kali㉿kali)-[~/Documentos/reversing]
└─$ python3         
Python 3.11.4 (main, Jun  7 2023, 10:13:09) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> print(int(0x86342))
549698

picoCTF{549698}

```

## Notas adicionales

## Referencias