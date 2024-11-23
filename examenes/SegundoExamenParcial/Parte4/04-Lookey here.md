# Lookey here

## Objetivo
Attackers have hidden information in a very large mass of data in the past, maybe they are still doing it.Download the data [here](https://artifacts.picoctf.net/c/126/anthem.flag.txt).

## Pistas

| No. Pistas | Pista                                                                |
| ---------- | -------------------------------------------------------------------- |
| 1          | Download the file and search for the flag based on the known prefix. |

## Solucion
```bash
┌──(kali㉿kali)-[~/Documentos/forensic/lookeyhere]
└─$ wget https://artifacts.picoctf.net/c/126/anthem.flag.txt 
--2024-04-09 16:33:43--  https://artifacts.picoctf.net/c/126/anthem.flag.txt
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.21.32, 13.249.21.46, 13.249.21.85, ...
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[13.249.21.32]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 108668 (106K) [application/octet-stream]
Grabando a: «anthem.flag.txt»

anthem.flag.txt       100%[======================>] 106.12K   599KB/s    en 0.2s    

2024-04-09 16:33:45 (599 KB/s) - «anthem.flag.txt» guardado [108668/108668]

                                                                                     
┌──(kali㉿kali)-[~/Documentos/forensic/lookeyhere]
└─$ file anthem.flag.txt 
anthem.flag.txt: Unicode text, UTF-8 text
                                                                                     
┌──(kali㉿kali)-[~/Documentos/forensic/lookeyhere]
└─$ cat anthem.flag.txt 
      ANTHEM

      by Ayn Rand


        CONTENTS

         PART ONE

         PART TWO

         PART THREE

         PART FOUR

         PART FIVE

         PART SIX

         PART SEVEN

         PART EIGHT

         PART NINE

         PART TEN

         PART ELEVEN

         PART TWELVE




      PART ONE

      It is a sin to write this. It is a sin to think words no others
      think and to put them down upon a paper no others are to see. It
      is base and evil. It is as if we were speaking alone to no ears
      but our own. And we know well that there is no transgression
      blacker than to do or think alone. We have broken the laws. The
      laws say that men may not write unless the Council of Vocations
      bid them so. May we be forgiven!
      ....
      ....
      ....
      And here, over the portals of my fort, I shall cut in the stone
      the word which is to be my beacon and my banner. The word which
      will not die, should we all perish in battle. The word which can
      never die on this earth, for it is the heart of it and the
      meaning and the glory.

      The sacred word:

      EGO



                                                                                     
┌──(kali㉿kali)-[~/Documentos/forensic/lookeyhere]
└─$ cat anthem.flag.txt | grep 'picoCTF'
      we think that the men of picoCTF{gr3p_15_@w3s0m3_2116b979}
      
```

## Notas adicionales

## Referencias