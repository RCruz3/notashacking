# ASCII FTW

## Objetivo
This program has constructed the flag using hex ascii values. Identify the flag text by disassembling the program.You can download the file from [here](https://artifacts.picoctf.net/c/508/asciiftw).

## Pistas


| No. Pista | Pista                                                                                        |
| --------- | -------------------------------------------------------------------------------------------- |
| 1         | The combined range of hex-ascii for English alphabets and numerical digits is from 30 to 7A. |
| 2         | Online hex-ascii converters can be helpful.                                                  |

## Solucion
```bash
┌──(kali㉿kali)-[~/Documentos/reversing]
└─$ wget https://artifacts.picoctf.net/c/508/asciiftw        
--2024-11-22 21:28:10--  https://artifacts.picoctf.net/c/508/asciiftw
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.100, 3.161.55.64, 3.161.55.26, ...
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[3.161.55.100]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 16752 (16K) [application/octet-stream]
Grabando a: «asciiftw.1»

asciiftw.1           100%[=====================>]  16.36K  --.-KB/s    en 0s      

2024-11-22 21:28:12 (150 MB/s) - «asciiftw.1» guardado [16752/16752]

                                                                                   
┌──(kali㉿kali)-[~/Documentos/reversing]
└─$ ls
asciiftw     debugger0_b               gdbtestdrive   vaultdoor1
asciiftw.1   disassembler-dump0_a.txt  needforspeed   vaultdoor3
asm          disassembler-dump0_b.txt  playfair.py    vaultdoor4
asm2         disassembler-dump0_c.txt  reversecipher  vaultdoor5
debugger0_a  disassembler-dump0_d.txt  safeopener2    vaultdoortraining
                                                                                   
┌──(kali㉿kali)-[~/Documentos/reversing]
└─$ cat asciiftw                        
@@@@�▒▒▒XX��   pp�-�=�=`h�-�=�=�888 XXXDDS�td888 P�td      DDQ�tdR�td�-�=�=PP/lib64/ld-linux-x86-64.so.2GNU�GNU��-���
                                  wI?^����UGNU��e�mZ 
                                                     2v � #"libc.so.6__stack_chk_failprintf__cxa_finalize__libc_start_mainGLIBC_2.2.5GLIBC_2.4_ITM_deregisterTMCloneTaP�`@�?�?�?�?�?�?�?��H�H��/H��t��H���5�/��%�/��h���������h�����������%�/D����%]/D����H�=��2/��H�=Y/H�R/H9�tH�/H��t  �����H�=)/H�5"/H)�H��H��?H��H�H��tH��.H����fD�����=�.u+UH�=�.H��t
              H�=�.�    ����d�����.]������w�����UH��H��0dH�%(H�E�1��E�p�E�i�E�c�E�o�E�C�E�T�E�F�E�{�E�A�E�S�E�C�E�I�E�I�E�_�E�I�E�S�E�_�E�E�E�A�E�S�E�Y�E�_�E�8�E�9�E���V����H�E�dH3%(t�1�����f.�D��AWL�=c+AVI��AUI��ATA��UH�-T+SL)�H������H��t1��L��L��D��A��H��H9�u�H�[]A\A]A^A_�ff.������H�H��The flag starts with %x
D���x0����@����`���`I���� ��������8zRx
                                     ����/D$4����0F▒J
�                                                    �?▒:*3$"\����t���� �q����E�C
D�(���eF�I▒�E �E(�D0�H8�G@n8A0A(B B▒B�P���` 
��▒����o���
�
 ▒�?0(� ������o8���o���o(���o�=0@GCC: (Ubuntu 9.4.0-1ubuntu1~20.04.1) 9.4.0▒8X|��(8
h
 (
 P`��   h �=�=�=▒�?@▒@�
                       ��! 7▒@F�=m`y�=������l!����=��=��=�  �▒�?�
                                                                 � � @3@�:Vj�@� @� �@e�▒▒@��/�▒@�i��@�"crtstuff.cderegister_tm_clones__do_global_dtors_auxcompleted.8061__do_global_dtors_aux_fini_array_entryframe_dummy__frame_dummy_init_array_entryasciiftw.c__FRAME_END____init_array_end_DYNAMIC__init_array_start__GNU_EH_FRAME_HDR_GLOBAL_OFFSET_TABLE___libc_csu_fini_ITM_deregisterTMCloneTable_edata__stack_chk_fail@@GLIBC_2.4printf@@GLIBC_2.2.5__libc_start_main@@GLIBC_2.2.5__data_start__gmon_start____dso_handle_IO_stdin_used__libc_csu_init__bss_startmain__TMC_END___ITM_registerTMCloneTable__cxa_finalize@@GLIBC_2.2.5.symtab.strtab.shstrtab.interp.note.gnu.property.note.gnu.build-id.note.ABI-tag.gnu.hash.dynsym.dynstr.gnu.version.gnu.version_r.rela.dyn.rela.plt.init.plt.got.plt.sec.text.fini.rodata.eh_frame_hdr.eh_frame.init_array.fini_array.dynamic.data.bss.comment▒▒#886XX$I|| W���o��a
                                                                ��▒i���q���o((~���o�  �    D�h ������=�-��?�@0���
                         @00+@00▒       p6$�8▒                                                                                   
┌──(kali㉿kali)-[~/Documentos/reversing]
└─$ objdump -d asciiftw | grep movb | grep -oE 0x.*, | xxd -p -r
picoCTF{ASCII_IS_EASY_8960F0AF}
```

## Notas adicionales

## Referencias