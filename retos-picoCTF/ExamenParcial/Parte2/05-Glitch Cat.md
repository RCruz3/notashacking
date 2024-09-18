# Glitch Cat

## Objetivo
Our flag printing service has started glitching! `$ nc saturn.picoctf.net 55826`

## Pistas

| No. Pista | Pista                                                                                        |
| --------- | -------------------------------------------------------------------------------------------- |
| 1         | ASCII is one of the most common encodings used in programming                                |
| 2         | We know that the glitch output is valid Python, somehow!                                     |
| 3         | Press Ctrl and c on your keyboard to close your connection and return to the command prompt. |


## Solucion
```bash
┌──(kali㉿kali)-[~/Descargas]
└─$ nc saturn.picoctf.net 55826
'picoCTF{gl17ch_m3_n07_' + chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) + chr(0x61) + chr(0x34) + chr(0x35) + chr(0x64) + '}'
                                                                                                  
┌──(kali㉿kali)-[~/Descargas]
└─$ ls
 Addadshashanammu       convertme.py   fixme2.py                     Obsidian-1.4.13.AppImage
 Addadshashanammu.zip   file           flag                          Obsidian-1.5.3.AppImage
 codebook.txt           file.1        'Obsidian-1.3.7(1).AppImage'   static
 code.py                fixme1.py      Obsidian-1.3.7.AppImage       strings
                                                                                                  
┌──(kali㉿kali)-[~/Descargas]
└─$ nano script.py                     
                                                                                                  
┌──(kali㉿kali)-[~/Descargas]
└─$ cat script.py              
flag_glitch_cat = chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) + chr(0x61) + chr(0x34) + chr(0x35) + chr(0x64)
print("picoCTF{gl17ch_m3_n07_" + flag_glitch_cat + "}")
                                                                                                  
┌──(kali㉿kali)-[~/Descargas]
└─$ python3 script.py 
picoCTF{gl17ch_m3_n07_9c42a45d}

```

## Notas adicionales

## Referencias