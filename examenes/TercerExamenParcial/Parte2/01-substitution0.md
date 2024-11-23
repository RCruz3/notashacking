# substitution0

## Objetivo
A message has come in but it seems to be all scrambled. Luckily it seems to have the key at the beginning. Can you crack this substitution cipher? Download the message [here](https://artifacts.picoctf.net/c/154/message.txt).

---
## Pistas

| No. Pista | Pista                                              |
| --------- | -------------------------------------------------- |
| 1         | Try a frequency attack. An online tool might help. |


## Solucion

```bash
┌──(kali㉿kali)-[~]
└─$ wget https://artifacts.picoctf.net/c/154/message.txt
--2024-06-08 21:35:04--  https://artifacts.picoctf.net/c/154/message.txt
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.225.11, 3.161.225.60, 3.161.225.62, ...
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[3.161.225.11]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 670 [application/octet-stream]
Grabando a: «message.txt»

message.txt             100%[============================>]     670  --.-KB/s    en 0s      

2024-06-08 21:35:18 (6.30 MB/s) - «message.txt» guardado [670/670]

                                                                                             
┌──(kali㉿kali)-[~]
└─$ cat message.txt
ZGSOCXPQUYHMILERVTBWNAFJDK 

Qctcnrel Mcptzlo ztebc, fuwq z ptzac zlo bwzwcmd zut, zlo gtenpqw ic wqc gccwmc
xtei z pmzbb szbc ul fqusq uw fzb clsmebco. Uw fzb z gcznwuxnm bsztzgzcnb, zlo, zw
wqzw wuic, nlhlefl we lzwntzmubwb—ex sentbc z ptczw rtukc ul z bsuclwuxus reulw
ex aucf. Wqctc fctc wfe tenlo gmzsh brewb lczt elc cjwtciuwd ex wqc gzsh, zlo z
melp elc lczt wqc ewqct. Wqc bszmcb fctc cjsccoulpmd qzto zlo pmebbd, fuwq zmm wqc
zrrcztzlsc ex gntlubqco pemo. Wqc fcupqw ex wqc ulbcsw fzb actd tcizthzgmc, zlo,
wzhulp zmm wqulpb ulwe selbuoctzwuel, U senmo qztomd gmzic Ynruwct xet qub eruluel
tcbrcswulp uw.

Wqc xmzp ub: ruseSWX{5NG5717N710L_3A0MN710L_357GX9XX} 
* Pasamos a la pagina en referencias

Decrypted text

HEREUPON LEGRAND AROSE, WITH A GRAVE AND STATELY AIR, AND BROUGHT ME THE BEETLE FROM A GLASS CASE IN WHICH IT WAS ENCLOSED. IT WAS A BEAUTIFUL SCARABAEUS, AND, AT THAT TIME, UNKNOWN TO NATURALISTS—OF COURSE A GREAT PRIZE IN A SCIENTIFIC POINT OF VIEW. THERE WERE TWO ROUND BLACK SPOTS NEAR ONE EXTREMITY OF THE BACK, AND A LONG ONE NEAR THE OTHER. THE SCALES WERE EXCEEDINGLY HARD AND GLOSSY, WITH ALL THE APPEARANCE OF BURNISHED GOLD. THE WEIGHT OF THE INSECT WAS VERY REMARKABLE, AND, TAKING ALL THINGS INTO CONSIDERATION, I COULD HARDLY BLAME JUPITER FOR HIS OPINION RESPECTING IT. THE FLAG IS: PICOCTF{5UB5717U710N_3V0LU710N_357BF9FF}
```

## Notas adicionales

## Referencias
* https://planetcalc.com/8047/