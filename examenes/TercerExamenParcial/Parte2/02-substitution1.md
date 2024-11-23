# substitution1

## Objetivo
A second message has come in the mail, and it seems almost identical to the first one. Maybe the same thing will work again. Download the message [here](https://artifacts.picoctf.net/c/182/message.txt).
## Pistas

| No. Pista | Pista                                                                        |
| --------- | ---------------------------------------------------------------------------- |
| 1         | Try a frequency attack                                                       |
| 2         | Do the punctuation and the individual words help you make any substitutions? |


## Solucion
```bash
┌──(kali㉿kali)-[~]
└─$ wget https://artifacts.picoctf.net/c/182/message.txt
--2024-06-08 22:07:50--  https://artifacts.picoctf.net/c/182/message.txt
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.225.3, 3.161.225.60, 3.161.225.11, ...
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[3.161.225.3]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 638 [application/octet-stream]
Grabando a: «message.txt.1»

message.txt.1           100%[============================>]     638  --.-KB/s    en 0s      

2024-06-08 22:07:51 (3.54 MB/s) - «message.txt.1» guardado [638/638]

                                                                                             
┌──(kali㉿kali)-[~]
└─$ cat message.txt.1
SYTe (eakdy tkd sjbyndr yar thjm) jdr j yobr kt skxbnyrd ersndzyo skxbryzyzkc. Skcyreyjcye jdr bdrercyrq gzya j ery kt sajhhrcmre gazsa yrey yarzd sdrjyzwzyo, yrsaczsjh (jcq mkkmhzcm) evzhhe, jcq bdklhrx-ekhwzcm jlzhzyo. Sajhhrcmre nenjhho skwrd j cnxlrd kt sjyrmkdzre, jcq garc ekhwrq, rjsa ozrhqe j eydzcm (sjhhrq j thjm) gazsa ze enlxzyyrq yk jc kchzcr eskdzcm erdwzsr. SYTe jdr j mdrjy gjo yk hrjdc j gzqr jddjo kt skxbnyrd ersndzyo evzhhe zc j ejtr, hrmjh rcwzdkcxrcy, jcq jdr akeyrq jcq bhjorq lo xjco ersndzyo mdknbe jdkncq yar gkdhq tkd tnc jcq bdjsyzsr. Tkd yaze bdklhrx, yar thjm ze: bzskSYT{TD3UN3CSO_4774SV5_4D3_S001_7JJ384LS}

* Pasamos a la pagina de referencias

Decrypted text

CTFS (SHORT FOR CAPTURE THE FLAG) ARE A TYPE OF COMPUTER SECURITY COMPETITION. CONTESTANTS ARE PRESENTED WITH A SET OF CHALLENGES WHICH TEST THEIR CREATIVITY, TECHNICAL (AND GOOGLING) SKILLS, AND PROBLEM-SOLVING ABILITY. CHALLENGES USUALLY COVER A NUMBER OF CATEGORIES, AND WHEN SOLVED, EACH YIELDS A STRING (CALLED A FLAG) WHICH IS SUBMITTED TO AN ONLINE SCORING SERVICE. CTFS ARE A GREAT WAY TO LEARN A WIDE ARRAY OF COMPUTER SECURITY SKILLS IN A SAFE, LEGAL ENVIRONMENT, AND ARE HOSTED AND PLAYED BY MANY SECURITY GROUPS AROUND THE WORLD FOR FUN AND PRACTICE. FOR THIS PROBLEM, THE FLAG IS: PICOCTF{FR3QU3NCY_4774CK5_4R3_C001_7AA384BC}
```

## Notas adicionales

## Referencias
* https://planetcalc.com/8047/