# Level X

## Objetivo
Now for something a little different. `0x2262c96b` is loaded into memory in the `main` function. Examine byte-wise the memory that the constant is loaded in by using the GDB command `x/4xb addr`. The flag is the four bytes as they are stored in memory. If you find the bytes `0x11 0x22 0x33 0x44` in the memory location, your flag would be: `picoCTF{0x11223344}`.Debug [this](https://artifacts.picoctf.net/c/531/debugger0_c).

## Pistas

| No. Pista | Pista                                                                                                                                                                         |
| --------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1         | You'll need to breakpoint the instruction after the memory load.                                                                                                              |
| 2         | Use the gdb command `x/4xb addr` with the memory location as the address `addr` to examine. [GDB manual page](https://ftp.gnu.org/old-gnu/Manuals/gdb/html_node/gdb_55.html). |
| 3         | Any registers in `addr` should be prepended with `$` like `$rbp`.                                                                                                             |
| 4         | Don't use square brackets for `addr`                                                                                                                                          |
| 5         | What is [endianness](https://en.wikipedia.org/wiki/Endianness)?                                                                                                               |

## Solucion
```bash
┌──(kali㉿kali)-[~/Documentos/reversing]
└─$ gdb debugger0_c
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
Reading symbols from debugger0_c...
(No debugging symbols found in debugger0_c)
(gdb) disassemble main
Dump of assembler code for function main:
   0x0000000000401106 <+0>:     endbr64
   0x000000000040110a <+4>:     push   %rbp
   0x000000000040110b <+5>:     mov    %rsp,%rbp
   0x000000000040110e <+8>:     mov    %edi,-0x14(%rbp)
   0x0000000000401111 <+11>:    mov    %rsi,-0x20(%rbp)
   0x0000000000401115 <+15>:    movl   $0x2262c96b,-0x4(%rbp)
   0x000000000040111c <+22>:    mov    -0x4(%rbp),%eax
   0x000000000040111f <+25>:    pop    %rbp
   0x0000000000401120 <+26>:    ret
End of assembler dump.
(gdb) b *(main+22)
Breakpoint 1 at 0x40111c
(gdb) run
Starting program: /home/kali/Documentos/reversing/debugger0_c 
[Thread debugging using libthread_db enabled]
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".

Breakpoint 1, 0x000000000040111c in main ()
(gdb) x/4xb $rbp-0x4
0x7fffffffddfc: 0x6b    0xc9    0x62    0x22

picoCTF{0x6bc96222}
```

## Notas adicionales

## Referencias