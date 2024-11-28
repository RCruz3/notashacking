# plumbing

## Objetivo
Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to `jupiter.challenges.picoctf.org 14291`.
## Pistas

| No. Pista | Pista                                                                                   |
| --------- | --------------------------------------------------------------------------------------- |
| 1         | Remember the flag format is picoCTF{XXXX}                                               |
| 2         | What's a pipe? No not that kind of pipe... This [kind](http://www.linfo.org/pipes.html) |


## Solucion
```bash
┌──(kali㉿kali)-[~/Documents/parcial1]
└─$ nc jupiter.challenges.picoctf.org 14291
Not a flag either
Again, I really don't think this is a flag
Not a flag either
I don't think this is a flag either
This is defintely not a flag
I don't think this is a flag either
Again, I really don't think this is a flag
Not a flag either
Not a flag either
I don't think this is a flag either
Not a flag either
This is defintely not a flag
This is defintely not a flag
Again, I really don't think this is a flag
Not a flag either
Not a flag either
Not a flag either
Not a flag either
This is defintely not a flag
This is defintely not a flag
Again, I really don't think this is a flag
Not a flag either
Not a flag either
Not a flag either
'
.....
.....
┌──(kali㉿kali)-[~/Documents/parcial1]
└─$ nc jupiter.challenges.picoctf.org 14291 | grep pico
picoCTF{digital_plumb3r_ea8bfec7}
```
## Notas adicionales

## Referencias