# vault-door-5

## Objetivo
In the last challenge, you mastered octal (base 8), decimal (base 10), and hexadecimal (base 16) numbers, but this vault door uses a different change of base as well as URL encoding! The source code for this vault is here: [VaultDoor5.java](https://jupiter.challenges.picoctf.org/static/d31ce4356bdfd15d33a9af7e35ab4d0a/VaultDoor5.java)
## Pistas

| No. Pista | Pista                                                                                                                        |
| --------- | ---------------------------------------------------------------------------------------------------------------------------- |
| 1         | You may find an encoder/decoder tool helpful, such as https://encoding.tools/                                                |
| 2         | Read the wikipedia articles on URL encoding and base 64 encoding to understand how they work and what the results look like. |


## Solucion
```
Copiamos el string expected y lo pegamos en cyberchef
al dejar solo la cadena detecta automaticamente el mensaje encryptado y nos aplica dos formulas
base64 y url decode y nos da:
c0nv3rt1ng_fr0m_ba5e_64_e3152bf4
```

## Notas adicionales

## Referencias