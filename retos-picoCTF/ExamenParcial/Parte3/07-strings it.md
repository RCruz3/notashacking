# strings it
## Objetivo
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/94d00153b0057d37da225ee79a846c62/strings) without running it?

## Pistas


| No. Pista | Pista                                          |
| --------- | ---------------------------------------------- |
| 1         | [strings](https://linux.die.net/man/1/strings) |

## Solucion
```bash
┌──(kali㉿kali)-[~/Descargas]
└─$ strings strings | grep "picoCTF"
picoCTF{5tRIng5_1T_d66c7bb7}

```

## Notas adicionales

## Referencias