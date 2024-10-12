# tunn3l_v1s10n

## Objetivo
We found this [file](https://mercury.picoctf.net/static/da18eed3d15fd04f7b076bdcecf15b27/tunn3l_v1s10n). Recover the flag.
## Pistas

| No. Pista | Pista                                |
| --------- | ------------------------------------ |
| 1         | Weird that it won't display right... |

## Solucion
```bash
┌──(kali㉿kali)-[~/Documentos/forensic/tunn3l_v1s10n]
└─$ mv tunn3l_v1s10n.1 tunn3l_vision.bmp
                                                                                                
┌──(kali㉿kali)-[~/Documentos/forensic/tunn3l_v1s10n]
└─$ open tunn3l_vision.bmp  
                                                                                                
┌──(kali㉿kali)-[~/Documentos/forensic/tunn3l_v1s10n]
└─$ ** Message: 00:01:51.645: Could not open file 'file:///home/kali/Documentos/forensic/tunn3l_v1s10n/tunn3l_vision.bmp': Tipo MIME no compatible

                                                                                                
┌──(kali㉿kali)-[~/Documentos/forensic/tunn3l_v1s10n]
└─$ hexeditor tunn3l_vision.bmp          
                                                                                                
┌──(kali㉿kali)-[~/Documentos/forensic/tunn3l_v1s10n]
└─$ open tunn3l_vision.bmp
```

## Notas adicionales


## Referencias