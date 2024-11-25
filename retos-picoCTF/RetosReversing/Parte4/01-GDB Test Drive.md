# GDB Test Drive

## Objetivo
Can you get the flag?Download this [binary](https://artifacts.picoctf.net/c/85/gdbme).Here's the test drive instructions:

- `$ chmod +x gdbme`
- `$ gdb gdbme`
- `(gdb) layout asm`
- `(gdb) break *(main+99)`
- `(gdb) run`
- `(gdb) jump *(main+104)`

## Pistas

| No. Pista | Pista |
| --------- | ----- |
|           |       |


## Solucion
```bash

(gdb) break *(main+99)
Breakpoint 1 at 0x132a
(gdb) run
Starting program: /home/kali/Documentos/reversing/gdbtestdrive/gdbme 
[Thread debugging using libthread_db enabled]
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".

Breakpoint 1, 0x000055555555532a in main ()
(gdb) jump *(main+104)
Continuing at 0x55555555532f.
picoCTF{d3bugg3r_dr1v3_197c378a}
```

## Notas adicionales

## Referencias