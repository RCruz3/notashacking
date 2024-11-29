# Sleuthkit Apprentice

## Objetivo
Download this disk image and find the flag.Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download compressed disk image](https://artifacts.picoctf.net/c/138/disk.flag.img.gz)

## Pistas

## Solucion
```bash
┌──(kali㉿kali)-[/tmp/SkeuAp]
└─$ gzip -d disk.flag.img.gz
                                                           
┌──(kali㉿kali)-[/tmp/SkeuAp]
└─$ mmls disk.flag.img      
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000360447   0000153600   Linux Swap / Solaris x86 (0x82)
004:  000:002   0000360448   0000614399   0000253952   Linux (0x83)
                                                           
┌──(kali㉿kali)-[/tmp/SkeuAp]
└─$ fls -o 360448 disk.flag.img -r
d/d 451:        home
d/d 11: lost+found
d/d 12: boot
d/d 1985:       etc
+ r/r 23:       group
+ r/r 24:       group-
+ r/r 25:       shadow
+ r/r 26:       shadow-
+ r/r 27:       passwd
+ r/r 28:       passwd-
+ r/r 29:       hosts
+ d/d 30:       zoneinfo
++ r/r 31:      UTC
+ r/r * 32(realloc):    resolv.conf
+ d/d 33:       keymap
++ r/r 34:      us.bmap.gz
+ r/r 35:       inittab
+ d/d 36:       conf.d
++ r/r * 493(realloc):  .apk.e0f21bd25c6c70139df2cde7bf1a36d489c455ae1ded76d7
++ r/r * 494(realloc):  .apk.0864ab1550d7450acef161ac8801ce25e921c2a9d91a6862
++ r/r * 495(realloc):  .apk.4a7da402791126ef582f6f6615a3ab47cac81b903da9fafc
++ r/r * 496(realloc):  .apk.c9958cbaf43ea23cd909f245cdcbdbcf30ee548c1700f691
...
...
┌──(kali㉿kali)-[/tmp/SkeuAp]
└─$ fls -o 360448 disk.flag.img -r 1995
r/r 2363:       .ash_history
d/d 3981:       my_folder
+ r/r * 2082(realloc):  flag.txt
+ r/r 2371:     flag.uni.txt
                                                           
┌──(kali㉿kali)-[/tmp/SkeuAp]
└─$ icat -o 360448 disk.flag.img 2371
picoCTF{by73_5urf3r_2f22df38}

```

## Notas adicionales

## Referencias