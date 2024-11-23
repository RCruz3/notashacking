# GDB baby step 2

## Objetivo
Can you figure out what is in the `eax` register at the end of the `main` function? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`. Debug [this](https://artifacts.picoctf.net/c/520/debugger0_b).
## Pistas

| No. Pista | Pista                                                                                                                                                           |
| --------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1         | You could calculate `eax` yourself, or you could set a breakpoint for after the calculcation and inspect `eax` to let the program do the heavy-lifting for you. |


## Solucion
```bash
┌──(kali㉿kali)-[~/Documentos/reversing]
└─$ wget https://artifacts.picoctf.net/c/520/debugger0_b
--2024-06-09 00:56:22--  https://artifacts.picoctf.net/c/520/debugger0_b
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.225.11, 3.161.225.3, 3.161.225.62, ...
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[3.161.225.11]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 16304 (16K) [application/octet-stream]
Grabando a: «debugger0_b»

debugger0_b          100%[====================>]  15.92K  --.-KB/s    en 0s      

2024-06-09 00:56:25 (67.2 MB/s) - «debugger0_b» guardado [16304/16304]

                                                                                  
┌──(kali㉿kali)-[~/Documentos/reversing]
└─$ gdb debugger0_b  
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
Reading symbols from debugger0_b...
(No debugging symbols found in debugger0_b)
(gdb) info function
All defined functions:

Non-debugging symbols:
0x0000000000401000  _init
0x0000000000401020  _start
0x0000000000401050  _dl_relocate_static_pie
0x0000000000401060  deregister_tm_clones
0x0000000000401090  register_tm_clones
0x00000000004010d0  __do_global_dtors_aux
0x0000000000401100  frame_dummy
0x0000000000401106  main
0x0000000000401150  __libc_csu_init
0x00000000004011c0  __libc_csu_fini
0x00000000004011c8  _fini
(gdb) disas main
Dump of assembler code for function main:
   0x0000000000401106 <+0>:     endbr64
   0x000000000040110a <+4>:     push   %rbp
   0x000000000040110b <+5>:     mov    %rsp,%rbp
   0x000000000040110e <+8>:     mov    %edi,-0x14(%rbp)
   0x0000000000401111 <+11>:    mov    %rsi,-0x20(%rbp)
   0x0000000000401115 <+15>:    movl   $0x1e0da,-0x4(%rbp)
   0x000000000040111c <+22>:    movl   $0x25f,-0xc(%rbp)
   0x0000000000401123 <+29>:    movl   $0x0,-0x8(%rbp)
   0x000000000040112a <+36>:    jmp    0x401136 <main+48>
   0x000000000040112c <+38>:    mov    -0x8(%rbp),%eax
   0x000000000040112f <+41>:    add    %eax,-0x4(%rbp)
   0x0000000000401132 <+44>:    addl   $0x1,-0x8(%rbp)
   0x0000000000401136 <+48>:    mov    -0x8(%rbp),%eax
   0x0000000000401139 <+51>:    cmp    -0xc(%rbp),%eax
   0x000000000040113c <+54>:    jl     0x40112c <main+38>
   0x000000000040113e <+56>:    mov    -0x4(%rbp),%eax
   0x0000000000401141 <+59>:    pop    %rbp
   0x0000000000401142 <+60>:    ret
End of assembler dump.
(gdb) quit
                                                                                  
┌──(kali㉿kali)-[~/Documentos/reversing]
└─$ python3
Python 3.11.4 (main, Jun  7 2023, 10:13:09) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> a = int(0x1e0da)
>>> b = int(0x25f)
>>> c = int(0x0)
>>> while (c < b):
... a = a + c
  File "<stdin>", line 2
    a = a + c
    ^
IndentationError: expected an indented block after 'while' statement on line 1
>>> while (c < b):
...     a = a + c
...     c += 1
... 
>>> print(a)
307019

picoCTF{307019}
```

## Notas adicionales

## Referencias