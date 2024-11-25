# Need For Speed

## Objetivo
The name of the game is [speed](https://www.youtube.com/watch?v=8piqd2BWeGI). Are you quick enough to solve this problem and keep it above 50 mph? [need-for-speed](https://jupiter.challenges.picoctf.org/static/27dd5548b14661f65ce3ac6a8a8f575b/need-for-speed).

## Pistas

| No. Pista | Pista                  |
| --------- | ---------------------- |
| 1         | What is the final key? |


## Solucion
```bash
┌──(kali㉿kali)-[~/Documentos/reversing]
└─$ chmod +x need-for-speed 
                                                                                                    
┌──(kali㉿kali)-[~/Documentos/reversing]
└─$ cp need-for-speed patched
                                                                                                    
┌──(kali㉿kali)-[~/Documentos/reversing]
└─$ r2 patched               
Warning: run r2 with -e bin.cache=true to fix relocations in disassembly
[0x00000660]> aaa
[x] Analyze all flags starting with sym. and entry0 (aa)
[x] Analyze function calls (aac)
[x] Analyze len bytes of instructions for references (aar)
[x] Finding and parsing C++ vtables (avrr)
[x] Type matching analysis for all functions (aaft)
[x] Propagate noreturn information (aanr)
[x] Use -AA or aaaa to perform additional experimental analysis.
[0x00000660]> afl
0x00000660    1 43           entry0
0x00000690    4 50   -> 40   sym.deregister_tm_clones
0x000006d0    4 66   -> 57   sym.register_tm_clones
0x00000720    5 58   -> 51   sym.__do_global_dtors_aux
0x00000650    1 6            sym.imp.__cxa_finalize
0x00000760    1 10           entry.init0
0x000009d0    1 2            sym.__libc_csu_fini
0x0000076a    6 135          sym.decrypt_flag
0x0000080e    1 33           sym.alarm_handler
0x00000610    1 6            sym.imp.puts
0x00000640    1 6            sym.imp.exit
0x00000630    1 6            sym.imp.__sysv_signal
0x00000620    1 6            sym.imp.alarm
0x000008d8    4 66           sym.header
0x000009d4    1 9            sym._fini
0x0000087d    1 47           sym.get_key
0x000007f1    3 29           sym.calculate_key
0x00000960    4 101          sym.__libc_csu_init
0x0000091a    1 62           main
0x0000082f    3 78           sym.set_timer
0x000008ac    1 44           sym.print_flag
0x000005d8    3 23           sym._init
0x00000600    1 6            sym.imp.putchar
0x00000000   12 459  -> 485  loc.imp._ITM_deregisterTMCloneTable
[0x00000660]> pdf
            ;-- section..text:
            ;-- .text:
            ;-- _start:
            ;-- rip:
┌ 43: entry0 (int64_t arg3);
│           ; arg int64_t arg3 @ rdx
│           0x00000660      31ed           xor ebp, ebp                ; [14] -r-x section size 882 named .text                                                                                         
│           0x00000662      4989d1         mov r9, rdx                 ; arg3
│           0x00000665      5e             pop rsi
│           0x00000666      4889e2         mov rdx, rsp
│           0x00000669      4883e4f0       and rsp, 0xfffffffffffffff0
│           0x0000066d      50             push rax
│           0x0000066e      54             push rsp
│           0x0000066f      4c8d055a0300.  lea r8, [sym.__libc_csu_fini] ; 0x9d0
│           0x00000676      488d0de30200.  lea rcx, [sym.__libc_csu_init] ; 0x960 ; "AWAVI\x89\xd7AUATL\x8d%&\x04 "                                                                                     
│           0x0000067d      488d3d960200.  lea rdi, [main]             ; 0x91a
│           0x00000684      ff1556092000   call qword [reloc.__libc_start_main] ; [0x200fe0:8]=0
└           0x0000068a      f4             hlt
[0x00000660]> s sym.get_key
[0x0000087d]> pdf
            ; CALL XREF from main @ 0x942
┌ 47: sym.get_key ();
│           0x0000087d      55             push rbp
│           0x0000087e      4889e5         mov rbp, rsp
│           0x00000881      488d3da00100.  lea rdi, str.Creating_key... ; 0xa28 ; "Creating key..." ; const char *s                                                                                     
│           0x00000888      e883fdffff     call sym.imp.puts           ; int puts(const char *s)
│           0x0000088d      b800000000     mov eax, 0
│           0x00000892      e85affffff     call sym.calculate_key
│           0x00000897      8905bf072000   mov dword [obj.key], eax    ; [0x20105c:4]=0
│           0x0000089d      488d3d940100.  lea rdi, str.Finished       ; 0xa38 ; "Finished" ; const char *s                                                                                             
│           0x000008a4      e867fdffff     call sym.imp.puts           ; int puts(const char *s)
│           0x000008a9      90             nop
│           0x000008aa      5d             pop rbp
└           0x000008ab      c3             ret
[0x0000087d]> s sym.calculate_key
[0x000007f1]> pdf
            ; CALL XREF from sym.get_key @ 0x892
┌ 29: sym.calculate_key ();
│           ; var uint32_t var_4h @ rbp-0x4
│           0x000007f1      55             push rbp
│           0x000007f2      4889e5         mov rbp, rsp
│           0x000007f5      c745fc401a80.  mov dword [var_4h], 0xd4801a40
│           ; CODE XREF from sym.calculate_key @ 0x807
│       ┌─> 0x000007fc      836dfc01       sub dword [var_4h], 1
│       ╎   0x00000800      817dfc200d40.  cmp dword [var_4h], 0xea400d20
│       └─< 0x00000807      75f3           jne 0x7fc
│           0x00000809      8b45fc         mov eax, dword [var_4h]
│           0x0000080c      5d             pop rbp
└           0x0000080d      c3             ret
[0x000007f1]> oo+
[0x000007f1]> s 0x000007f5
[0x000007f5]> pd 1
│           0x000007f5      c745fc401a80.  mov dword [var_4h], 0xd4801a40
[0x000007f5]> wa mov dword [rbp-0x4], 0xea400d21
Written 7 byte(s) (mov dword [rbp-0x4], 0xea400d21) = wx c745fc210d40ea
[0x000007f5]> q
                                                                                                    
┌──(kali㉿kali)-[~/Documentos/reversing]
└─$ ./patched                
Keep this thing over 50 mph!
============================

Creating key...
Finished
Printing flag:
PICOCTF{Good job keeping bus #1f2ac4ec speeding along!}
```

## Notas adicionales

## Referencias