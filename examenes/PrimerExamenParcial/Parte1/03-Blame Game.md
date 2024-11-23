# Blame Game

## Objetivo
Someone's commits seems to be preventing the program from working. Who is it? You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/158/challenge.zip)

## Pistas

| No. Pista | Pista                                                                                                     |
| --------- | --------------------------------------------------------------------------------------------------------- |
| 1         | In collaborative projects, many users can make many changes. How can you see the changes within one file? |
| 2         | Read the chapter on Git from the picoPrimer [here](https://primer.picoctf.org/#_git_version_control).     |
| 3         | You can use `python3 <file>.py` to try running the code, though you won't need to for this challenge.     |


## Solucion
```bash
──(kali㉿kali)-[~/Documentos/retosPicoPrimerParcial/blameGame]
└─$ ls
challenge.zip  drop-in
                                                                                             
┌──(kali㉿kali)-[~/Documentos/retosPicoPrimerParcial/blameGame]
└─$ cd drop-in  
                                                                                             
┌──(kali㉿kali)-[~/Documentos/retosPicoPrimerParcial/blameGame/drop-in]
└─$ ls
message.py
                                                                                             
┌──(kali㉿kali)-[~/Documentos/retosPicoPrimerParcial/blameGame/drop-in]
└─$ python3 message.py 
  File "/home/kali/Documentos/retosPicoPrimerParcial/blameGame/drop-in/message.py", line 1
    print("Hello, World!"
         ^
SyntaxError: '(' was never closed
                                                                                             
┌──(kali㉿kali)-[~/Documentos/retosPicoPrimerParcial/blameGame/drop-in]
└─$ git init
Reinicializado el repositorio Git existente en /home/kali/Documentos/retosPicoPrimerParcial/blameGame/drop-in/.git/
                                                                                             
┌──(kali㉿kali)-[~/Documentos/retosPicoPrimerParcial/blameGame/drop-in]
└─$ git log | grep picoCTF{
Author: picoCTF{@sk_th3_1nt3rn_2c6bf174} <ops@picoctf.com>
```

## Notas adicionales

## Referencias
* https://primer.picoctf.org/#_git_version_control