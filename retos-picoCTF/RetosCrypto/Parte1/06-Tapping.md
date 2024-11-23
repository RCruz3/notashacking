# Tapping

## Objetivo
Theres tapping coming in from the wires. What's it saying `nc jupiter.challenges.picoctf.org 9422`.

## Pistas

| No. Pistas | Pista                                       |
| ---------- | ------------------------------------------- |
| 1          | What kind of encoding uses dashes and dots? |
| 2          | The flag is in the format PICOCTF{}         |


## Solucion
```bash
┌──(kali㉿kali)-[~/Documentos/crypto]
└─$ nc jupiter.challenges.picoctf.org 9422  
.--. .. -.-. --- -.-. - ..-. { -- ----- .-. ... ...-- -.-. ----- -.. ...-- .---- ... ..-. ..- -. ..--- -.... ---.. ...-- ---.. ..--- ....- -.... .---- ----- } 

pasandolo a cyber chef en "From Morse Code" nos da:
PICOCTF{M0RS3C0D31SFUN2683824610}
```

## Notas adicionales

## Referencias