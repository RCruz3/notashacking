# It is my Birthday

## Objetivo
I sent out 2 invitations to all of my friends for my birthday! I'll know if they get stolen because the two invites look similar, and they even have the same md5 hash, but they are slightly different! You wouldn't believe how long it took me to find a collision. Anyway, see if you're invited by submitting 2 PDFs to my website. [http://mercury.picoctf.net:55343/](http://mercury.picoctf.net:55343/)

## Pistas

| No. Pista | Pista |
| --------- | ----- |
|           |       |


## Solucion
```bash
──(kali㉿kali)-[~/Downloads]
└─$ ls
erase  hello  Obsidian-1.7.7.AppImage
                                                           
┌──(kali㉿kali)-[~/Downloads]
└─$ mv erase erase.pdf
                                                           
┌──(kali㉿kali)-[~/Downloads]
└─$ mv hello hello.pdf
                                                           
┌──(kali㉿kali)-[~/Downloads]
└─$ ls
erase.pdf  hello.pdf  Obsidian-1.7.7.AppImage

```
* Subir los dos archivos .pdf en la pagina
* Encontrar la bandera
`picoCTF{c0ngr4ts_u_r_1nv1t3d_aad886b9}`

## Notas adicionales

## Referencias