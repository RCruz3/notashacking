# Tab, Tab, Attack

## Objetivo
Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames: [Addadshashanammu.zip](https://mercury.picoctf.net/static/659efd595171e4c40378be6a2e9b7298/Addadshashanammu.zip)

## Pistas

| No. Pista | Pista                                                                                 |
| --------- | ------------------------------------------------------------------------------------- |
| 1         | After `unzip`ing, this problem can be solved with 11 button-presses...(mostly Tab)... |


## Solucion
```bash
┌──(kali㉿kali)-[~]
└─$ ls
Descargas   inc.asm         incremento.o     suma_incremento.asm
Desktop     inc_dec         ltdis.sh         suma_incremento_decremento
Documentos  inc_dec.asm     Música           suma_incremento_decremento.asm
Escritorio  inc_dec.o       Plantillas       suma_incremento_decremento.o
flag        inc.o           Público          suma_incremento.o
Imágenes    incremento      static           Vídeos
inc         incremento.asm  suma_incremento  warm
                                                                                                  
┌──(kali㉿kali)-[~]
└─$ cd Descargas               
                                                                                                  
┌──(kali㉿kali)-[~/Descargas]
└─$ ls
 Addadshashanammu.zip  'Obsidian-1.3.7(1).AppImage'   Obsidian-1.4.13.AppImage   static
 flag                   Obsidian-1.3.7.AppImage       Obsidian-1.5.3.AppImage
                                                                                                  
┌──(kali㉿kali)-[~/Descargas]
└─$ unzip Addadshashanammu.zip 
Archive:  Addadshashanammu.zip
   creating: Addadshashanammu/
   creating: Addadshashanammu/Almurbalarammi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
  inflating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet  
                                                                                                  
┌──(kali㉿kali)-[~/Descargas]
└─$ ls     
 Addadshashanammu      'Obsidian-1.3.7(1).AppImage'   Obsidian-1.5.3.AppImage
 Addadshashanammu.zip   Obsidian-1.3.7.AppImage       static
 flag                   Obsidian-1.4.13.AppImage
                                                                                                  
┌──(kali㉿kali)-[~/Descargas]
└─$ cd Addadshashanammu 
                                                                                                  
┌──(kali㉿kali)-[~/Descargas/Addadshashanammu]
└─$ ls
Almurbalarammi
                                                                                                  
┌──(kali㉿kali)-[~/Descargas/Addadshashanammu]
└─$ cd Almurbalarammi  
                                                                                                  
┌──(kali㉿kali)-[~/Descargas/Addadshashanammu/Almurbalarammi]
└─$ cd Ashalmimilkala 
                                                                                                  
┌──(kali㉿kali)-[~/Descargas/Addadshashanammu/Almurbalarammi/Ashalmimilkala]
└─$ cd Assurnabitashpi 
                                                                                                  
┌──(kali㉿kali)-[~/…/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi]
└─$ cd Maelkashishi   
                                                                                                  
┌──(kali㉿kali)-[~/…/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi]
└─$ cd Onnissiralis 
8#TT 1tt$D���o�N                                                                                  
�� ��0)@▒ kali)-(;▒�                                                                                                   
┌──(kali㉿kali)-[~/…/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└─$ ls
fang-of-haynekhtnamet
]
└─$ file fang-of-haynekhtnamet 
fang-of-haynekhtnamet: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=e34ce4e4ee2f7ce7fb251c8f5ab036da9882bc55, not stripped
                                                                                                  
┌──(kali㉿kali)-[~/…/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└─$ ./fang-of-haynekhtnamet 
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_524e3dc4}
                                                                                                  
┌──(kali㉿kali)-[~/…/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└─$ 

```

## Notas adicionales

## Referencias