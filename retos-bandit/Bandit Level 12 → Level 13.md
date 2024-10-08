# Bandit Level 12 → Level 13

## Objetivo
The password for the next level is stored in the file **data.txt**, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!)

## Datos de acceso al nivel
```
bandit12
JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
```

## Solucion
```bash
bandit12@bandit:~$ ls
data.txt
bandit12@bandit:~$ mkdir /tmp/rcruz3
bandit12@bandit:~$ cd /tmp/rcruz3
bandit12@bandit:/tmp/rcruz3$ ls
bandit12@bandit:/tmp/rcruz3$ cd
bandit12@bandit:~$ cp data.txt /tmp/rcruz3
bandit12@bandit:~$ ls
data.txt
bandit12@bandit:~$ cd /tmp/rcruz3
bandit12@bandit:/tmp/rcruz3$ ls
data.txt
bandit12@bandit:/tmp/rcruz3$ cat data.txt 
00000000: 1f8b 0808 2773 4564 0203 6461 7461 322e  ....'sEd..data2.
00000010: 6269 6e00 0145 02ba fd42 5a68 3931 4159  bin..E...BZh91AY
00000020: 2653 597b 4f96 5f00 0018 ffff fd6f e7ed  &SY{O._......o..
00000030: bff7 bef7 9fdb d7ca ffbf edff 8ded dfd7  ................
00000040: bfe7 bbff bfdb fbff ffbf ff9f b001 3b56  ..............;V
00000050: 0400 0068 0064 3400 d341 a000 0680 0699  ...h.d4..A......
00000060: 0000 69a0 0000 1a00 1a0d 0034 0034 d3d4  ..i........4.4..
00000070: d1a3 d464 6834 6403 d469 b422 0d00 3400  ...dh4d..i."..4.
00000080: 1a68 068d 3403 4d06 8d00 0c80 00f5 0003  .h..4.M.........
00000090: 4031 3119 00d0 1a68 1a34 c86d 4640 00d0  @11....h.4.mF@..
000000a0: 0007 a80d 000d 00e9 a340 d034 0341 a000  .........@.4.A..
000000b0: 0699 07a9 881e a0d0 da80 6834 0c43 4068  ..........h4.C@h
000000c0: 6432 0340 0c80 6800 0346 8006 8000 d034  d2.@..h..F.....4
000000d0: 0001 f0e1 810e 1958 b7a4 92c7 640e 421a  .......X....d.B.
000000e0: a147 6142 a67e 3603 a756 3ba9 1b08 e034  .GaB.~6..V;....4
000000f0: 41fd 1247 661d b380 00b7 cd8c b23e b6b2  A..Gf........>..
00000100: 1947 e803 0be5 6077 a542 e9ea 7810 29f0  .G....`w.B..x.).
00000110: 429d e1d7 ad8b 0b78 056b e37c 06df 4917  B......x.k.|..I.
00000120: 9b46 f69d 4473 80b4 edc2 ee10 04e3 3e52  .F..Ds........>R
00000130: dd34 2244 08cb 5e64 9314 9521 505e e767  .4"D..^d...!P^.g
00000140: 9021 d029 85e7 9ce2 d1ce d44f 5ec5 f6d6  .!.).......O^...
00000150: d918 de31 f1f5 d149 4695 0937 d06b f046  ...1...IF..7.k.F
00000160: 789d 1bd0 ca69 11eb 2c9a 3290 3d9e 0511  x....i..,.2.=...
00000170: 6cad 205b edc8 c4b5 4691 379a 5978 58c3  l. [....F.7.YxX.
00000180: 4846 a4a0 3ba5 a89a a794 1f93 c588 8160  HF..;..........`
00000190: 016e 2504 2c74 643b 5046 4154 751c 33b1  .n%.,td;PFATu.3.
000001a0: c3e5 53d8 a959 5fdc 6c12 f2bd 02f3 2d83  ..S..Y_.l.....-.
000001b0: b965 3188 0d3c b097 4156 e950 9d49 64f6  .e1..<..AV.P.Id.
000001c0: da4a 2db5 a4ea 5365 27c0 1e79 8109 5f31  .J-...Se'..y.._1
000001d0: c184 46c9 74a5 f923 5ea1 6861 f058 226c  ..F.t..#^.ha.X"l
000001e0: 3df6 5d10 d11f d966 77c9 e488 448c 5a6f  =.]....fw...D.Zo
000001f0: 2c10 410b 4280 140a 0818 8afa 0cfa 8bf7  ,.A.B...........
00000200: ad34 3308 4077 6552 9849 378e 7d85 1fd8  .43.@weR.I7.}...
00000210: f287 1238 7639 11e2 f1e6 483b 7548 25e2  ...8v9....H;uH%.
00000220: 7de4 24ff 1a69 0b85 4b4c ebd0 1231 a512  }.$..i..KL...1..
00000230: f9fb 109c e7ea d932 98fd eb76 f4f8 fa29  .......2...v...)
00000240: 967c e152 9c69 c607 6207 eaef 2095 9441  .|.R.i..b... ..A
00000250: a64e 9ffc 5dc9 14e1 4241 ed3e 597c 9f2e  .N..]...BA.>Y|..
00000260: f0c8 4502 0000                           ..E...
bandit12@bandit:/tmp/rcruz3$ cat data.txt | xxd -r > datos
bandit12@bandit:/tmp/rcruz3$ ls
data.txt  datos
bandit12@bandit:/tmp/rcruz3$ cat datos
4▒h�4M�h4d�i�"��BZh91AY&SY{O�_▒���o�����������������׿������������;Vhd4�A���i�▒▒
��@�4A������ڀh4▒4�mF@��
               C@hd2@
                     �hF���4���X����dB▒�GaB�~6�V;4A�Gf����>��G�
                                                               �`w�B��x)�B��׭�
                                                                              xk�|�I�F��Ds������>R�4"�^d��!P^�g�!�)�������O^����▒�1���IF� 7�k�Fx��i�,�2�=�l� [��ĵF�7�YxX�HF��;������ň�`n%,td;PFATu3�<��AV�P�Id��J-���Se'�y� _1��F�t��#^�ha�X"l=�]��fw���D�Zo,A
                                                          B�
▒��
   ����4@weR�I7�}����8v9���H;uH%�}�$�▒i
                                       �KL��1�������2���v���)�|�R�i�b�� ��A�N��]��BA�>Y|�.��Ebandit12@bandit:/tmp/rcruz3$ file datos                                                                
datos: gzip compressed data, was "data2.bin", last modified: Sun Apr 23 18:04:23 2023, max compression, from Unix, original size modulo 2^32 581
bandit12@bandit:/tmp/rcruz3$ mv datos.gz
mv: missing destination file operand after 'datos.gz'
Try 'mv --help' for more information.
bandit12@bandit:/tmp/rcruz3$ mv datos datos.gz
bandit12@bandit:/tmp/rcruz3$ ls
data.txt  datos.gz
bandit12@bandit:/tmp/rcruz3$ file datos
datos: cannot open `datos' (No such file or directory)
bandit12@bandit:/tmp/rcruz3$ file datos.gz
datos.gz: gzip compressed data, was "data2.bin", last modified: Sun Apr 23 18:04:23 2023, max compression, from Unix, original size modulo 2^32 581
bandit12@bandit:/tmp/rcruz3$ ls
data.txt  datos.gz
bandit12@bandit:/tmp/rcruz3$ -gzip -d datos.gz
Command '-gzip' not found, did you mean:
  command 'bgzip' from deb tabix (1.13+ds-2build1)
  command 'igzip' from deb isal (2.30.0-4)
  command 'gzip' from deb gzip (1.10-4ubuntu4.1)
Try: apt install <deb name>
bandit12@bandit:/tmp/rcruz3$ ls
data.txt  datos.gz
bandit12@bandit:/tmp/rcruz3$ gzip -d datos.gz
bandit12@bandit:/tmp/rcruz3$ ls
data.txt  datos
bandit12@bandit:/tmp/rcruz3$ file datos
datos: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/rcruz3$ mv datos datos.bz2
bandit12@bandit:/tmp/rcruz3$ bzip2 -d datos.bz2
bandit12@bandit:/tmp/rcruz3$ ls
data.txt  datos
bandit12@bandit:/tmp/rcruz3$ file datos
datos: gzip compressed data, was "data4.bin", last modified: Sun Apr 23 18:04:23 2023, max compression, from Unix, original size modulo 2^32 20480
bandit12@bandit:/tmp/rcruz3$ mv datos datos.gz
bandit12@bandit:/tmp/rcruz3$ gzip -d datos.gz
bandit12@bandit:/tmp/rcruz3$ file datos
datos: POSIX tar archive (GNU)
bandit12@bandit:/tmp/rcruz3$ mv datos datos.tar
bandit12@bandit:/tmp/rcruz3$ tar xf datos.tar
bandit12@bandit:/tmp/rcruz3$ ls
data5.bin  data.txt  datos.tar
bandit12@bandit:/tmp/rcruz3$ rm datos.tar
bandit12@bandit:/tmp/rcruz3$ ls
data5.bin  data.txt
bandit12@bandit:/tmp/rcruz3$ file data5.bin
data5.bin: POSIX tar archive (GNU)
bandit12@bandit:/tmp/rcruz3$ mv data5.bin data5.tar
bandit12@bandit:/tmp/rcruz3$ ls
data5.tar  data.txt
bandit12@bandit:/tmp/rcruz3$ tar xf data5.tar
bandit12@bandit:/tmp/rcruz3$ ls
data5.tar  data6.bin  data.txt
bandit12@bandit:/tmp/rcruz3$ rm data5.tar
bandit12@bandit:/tmp/rcruz3$ ls
data6.bin  data.txt
bandit12@bandit:/tmp/rcruz3$ file data6.bin
data6.bin: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/rcruz3$ mv data6.bin data6.bz2
bandit12@bandit:/tmp/rcruz3$ ls
data6.bz2  data.txt
bandit12@bandit:/tmp/rcruz3$ bzip2 -d data6.bz2
bandit12@bandit:/tmp/rcruz3$ ls
data6  data.txt
bandit12@bandit:/tmp/rcruz3$ file data6
data6: POSIX tar archive (GNU)
bandit12@bandit:/tmp/rcruz3$ tar xf data6.tar
tar: data6.tar: Cannot open: No such file or directory
tar: Error is not recoverable: exiting now
bandit12@bandit:/tmp/rcruz3$ mv data6 data6.tar
bandit12@bandit:/tmp/rcruz3$ ls
data6.tar  data.txt
bandit12@bandit:/tmp/rcruz3$ tar xf data6.tar
bandit12@bandit:/tmp/rcruz3$ ls
data6.tar  data8.bin  data.txt
bandit12@bandit:/tmp/rcruz3$ rm data6.tar
bandit12@bandit:/tmp/rcruz3$ file data8.bin
data8.bin: gzip compressed data, was "data9.bin", last modified: Sun Apr 23 18:04:23 2023, max compression, from Unix, original size modulo 2^32 49
bandit12@bandit:/tmp/rcruz3$ mv data8.bin data8.gz
bandit12@bandit:/tmp/rcruz3$ ls
data8.gz  data.txt
bandit12@bandit:/tmp/rcruz3$ gzip -d data8.gz
bandit12@bandit:/tmp/rcruz3$ ls
data8  data.txt
bandit12@bandit:/tmp/rcruz3$ file data8
data8: ASCII text
bandit12@bandit:/tmp/rcruz3$ cat dat8
cat: dat8: No such file or directory
bandit12@bandit:/tmp/rcruz3$ cat data8
The password is wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
bandit12@bandit:/tmp/rcruz3$
```

## Notas adicionales
|Commando| Descripcion|
|-----------|-------------|
|ls| lista los archivos de la carpeta actual|
|mv|  renombrar|
|cp|  copiar|
|rm|  eliminar|
|gzip|  comprime o extrae archivos del tipo gzip |
|bzip2|  comprime o extrae archivos del tipo bzip2 |
|tar|  comprime o extrae archivos del tipo tar |
* tar genera un nuevo archivo

## Referencias
* https://en.wikipedia.org/wiki/Hex_dump