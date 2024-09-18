# Wave a Flag

## Objetivo
Can you invoke help flags for a tool or binary? [This program](https://mercury.picoctf.net/static/a14be2648c73e3cda5fc8490a2f476af/warm) has extraordinarily helpful information...

## Pistas

| No. Pista | Pista                                                                                                                                                                   |
| --------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1         | This program will only work in the webshell or another Linux computer.                                                                                                  |
| 2         | To get the file accessible in your shell, enter the following in the Terminal prompt: `$ wget https://mercury.picoctf.net/static/a14be2648c73e3cda5fc8490a2f476af/warm` |
| 3         | Run this program by entering the following in the Terminal prompt: `$ ./warm`, but you'll first have to make it executable with `$ chmod +x warm`                       |
| 4         | -h and --help are the most common arguments to give to programs to get more information from them!                                                                      |
| 5         | Not every program implements help features like -h and --help.                                                                                                          |

## Solucion
```bash
┌──(kali㉿kali)-[~]
└─$ ls
Descargas   inc          incremento      suma_incremento                 Vídeos
Desktop     inc.asm      incremento.asm  suma_incremento.asm             warm
Documentos  inc_dec      incremento.o    suma_incremento_decremento
Escritorio  inc_dec.asm  Música          suma_incremento_decremento.asm
flag        inc_dec.o    Plantillas      suma_incremento_decremento.o
Imágenes    inc.o        Público         suma_incremento.o
                                                                                             
┌──(kali㉿kali)-[~]
└─$ chmod +x warm
                                                                                             
┌──(kali㉿kali)-[~]
└─$ ./warm
Hello user! Pass me a -h to learn what I can do!
                                                                                             
┌──(kali㉿kali)-[~]
└─$ ls
Descargas   inc          incremento      suma_incremento                 Vídeos
Desktop     inc.asm      incremento.asm  suma_incremento.asm             warm
Documentos  inc_dec      incremento.o    suma_incremento_decremento
Escritorio  inc_dec.asm  Música          suma_incremento_decremento.asm
flag        inc_dec.o    Plantillas      suma_incremento_decremento.o
Imágenes    inc.o        Público         suma_incremento.o
                                                                                             
┌──(kali㉿kali)-[~]
└─$ ./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_755f3544}
```


## Notas adicionales

## Referencias