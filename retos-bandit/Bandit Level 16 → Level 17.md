# Bandit Level 16 → Level 17

## Objetivo
The credentials for the next level can be retrieved by submitting the password of the current level to **a port on localhost in the range 31000 to 32000**. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.

## Datos de acceso al nivel
```
bandit16
JQttfApK4SeyHwDlI9SXGR50qclOAil1
```

## Solucion
```bash
bandit16@bandit:~$ nmap -p 31000-32000 localhost
Starting Nmap 7.80 ( https://nmap.org ) at 2023-09-27 14:38 UTC
Nmap scan report for localhost (127.0.0.1)
Host is up (0.00017s latency).
Not shown: 996 closed ports
PORT      STATE SERVICE
31046/tcp open  unknown
31518/tcp open  unknown
31691/tcp open  unknown
31790/tcp open  unknown
31960/tcp open  unknown

Nmap done: 1 IP address (1 host up) scanned in 0.08 seconds
bandit16@bandit:~$ openssl s_client -connect localhost:31790
CONNECTED(00000003)
Cant use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Sep 26 18:07:57 2023 GMT
verify return:1
depth=0 CN = localhost
notAfter=Sep 26 18:07:57 2023 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Sep 26 18:06:57 2023 GMT; NotAfter: Sep 26 18:07:57 2023 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIERiuWyjANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjMwOTI2MTgwNjU3WhcNMjMwOTI2MTgwNzU3WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQDm
tnxHOOc9maz2HO6CVkXgkD6/jrrhZ29LtfH6GeLwaUZ9CZcBVOBd20dUe9BaEbt6
gDFarAMLfL1G+Zr73vGTJKeV4XqhEl+pyQLQNuJjO5N0OweaitFVTFBDhHteHQkn
/j+2y1y4kbGh9R7mGjA57Xk28VpOpF1ZJfoX5cSEmF0mdV1GMYAWnaOqtkEs6yQb
aHyYNeUYeeax/XmHr2eXNbnstgE6hP/eSbQbKc6Y9mUCCifISLFh+EUvxUJTd/95
5qzEnMakruJYPu0YObTV7n/JZI/3HFbz4LOvxaHA5exhk+HehW3p8joxUHXmWt4+
bhKM97rpqgaLSHxFJqC5AgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQC/
Kq5TxjjZE2YrpPQLS1vQjGZ2wlL/ooG2GUHZGMiPX6/ABW6O7Yib9uLJK6o8kLVR
YDP0+NjoFL795k97ut0Q2YS4ULO3AcZlVoyLbI94YJsri5ABjYgs0s3M2pa+u2Eo
EzaFHO/iCvQ+Iqr1/J5B/xBtAcSdk45RvMBoYJOApVO58xYhBglWiL+ObetGbvd8
RyWHKKiQe9UDhur08J6Y3OJ8QQc7xby0pTmQTPAr+jNtnAjKRgC8jcA0i+U+E6nW
eUtAo68v+zh1b3znOghZblVJMab1R8Ej+xBN2PBHWPeJea6pVdMUJTTUPX6GVD6R
0SUydJN33p3ZcMO9UpXa
-----END CERTIFICATE-----
subject=CN = localhost
issuer=CN = localhost
---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA-PSS
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 1339 bytes and written 373 bytes
Verification error: certificate has expired
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Server public key is 2048 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 10 (certificate has expired)
---
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: B433AC201C609112AB9F477520A245EDC30381A86991FE5107B2BA79691CCBF0
    Session-ID-ctx: 
    Resumption PSK: 5EF6D49928CD853123A4330EFC0070A51A5E5C5BAE8CFD0A64E4C296D997B88D68071954AD24604F421B09E69F09FF78
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 9e 0e 4b 3f 0c 7b 8d 1d-8d a4 b6 56 18 a5 31 61   ..K?.{.....V..1a
    0010 - 28 19 ce e1 5e 9c 7f 09-63 84 9a c8 a8 f6 96 d2   (...^...c.......
    0020 - 78 98 98 8c 96 b7 1b b8-37 09 5f 35 6d 38 f9 75   x.......7._5m8.u
    0030 - b6 54 ab 15 a3 8c 8c 81-49 80 10 0c 7b 41 8b 5c   .T......I...{A.\
    0040 - 46 d0 c2 bd bb 5f 87 87-fc 3e c3 ca f5 e7 65 38   F...._...>....e8
    0050 - 41 39 d9 7a 84 f2 45 f4-49 4d 97 03 78 33 28 29   A9.z..E.IM..x3()
    0060 - a7 e1 1b 8b 58 a8 69 5c-78 75 c7 38 c3 5a 45 48   ....X.i\xu.8.ZEH
    0070 - 6d f6 f0 12 29 c8 64 e7-d1 4e a0 d4 7a 77 9c 0d   m...).d..N..zw..
    0080 - 25 b7 85 9a 4a c2 64 de-74 94 89 23 89 81 e9 fa   %...J.d.t..#....
    0090 - 56 42 fb 16 74 41 80 5a-da ad 3a a2 86 fc 8f d5   VB..tA.Z..:.....
    00a0 - 6e 63 73 68 5e c1 ee 3a-6f 00 9a 64 14 9e c6 89   ncsh^..:o..d....
    00b0 - 7b 76 bd 4a f0 d0 57 b4-ed 80 ff a3 cd 81 a2 d9   {v.J..W.........
    00c0 - 28 77 42 76 53 69 98 f8-2c d1 73 a7 46 0e 8c 09   (wBvSi..,.s.F...

    Start Time: 1695825656
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 31484B1B4AD5DC4434551CD3E4AC00E44C34D715E38FC1A5006E14BFC3AAF456
    Session-ID-ctx: 
    Resumption PSK: 1ED6886A1AD3ABB446595477C301B29AC34E96A12A1BAD980CF9076D7A6F81B06105525A35EDCD60CF1C67968B3B6522
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 9e 0e 4b 3f 0c 7b 8d 1d-8d a4 b6 56 18 a5 31 61   ..K?.{.....V..1a
    0010 - c3 6a bc bf ca 2e 5d dd-69 82 ad 0d a3 b2 c9 51   .j....].i......Q
    0020 - 72 16 3d 44 48 41 64 33-c4 06 4b ed 5c 51 7c d9   r.=DHAd3..K.\Q|.
    0030 - 13 bc ad 9a 18 75 93 b8-6a a3 37 1c a5 e2 ba c6   .....u..j.7.....
    0040 - ed 8a 80 a6 7e 5b 3b 6b-db 6b 69 9e 22 43 6f c6   ....~[;k.ki."Co.
    0050 - 97 56 53 a9 11 22 7c 83-9f db cb 4c 1b 66 3b f9   .VS.."|....L.f;.
    0060 - 3d 71 c8 20 5d e3 fe 68-b0 50 15 84 88 a0 5f dd   =q. ]..h.P...._.
    0070 - fc df 3c 68 7b 8e e3 e0-d3 6d 30 46 d0 44 36 9a   ..<h{....m0F.D6.
    0080 - e7 90 12 46 bb be 9b 2a-c8 cc e7 5a 3d 82 cd 15   ...F...*...Z=...
    0090 - 0c a4 51 5f 1c 9f 06 c4-a9 dd 65 58 4e 6d e5 84   ..Q_......eXNm..
    00a0 - 08 9c 24 d0 66 14 b0 5a-9a 2f 71 a7 d3 14 bb 25   ..$.f..Z./q....%
    00b0 - 01 bd 24 3e 1e b6 5f c2-a3 09 f8 5f be e4 61 46   ..$>.._...._..aF
    00c0 - 5a a2 19 9d 49 71 b7 f0-9d f0 2f fd 84 aa 48 43   Z...Iq..../...HC

    Start Time: 1695825656
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
JQttfApK4SeyHwDlI9SXGR50qclOAil1
Correct!
-----BEGIN RSA PRIVATE KEY-----
MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
Ja6Lzb558YW3FZl87ORiO+rW4LCDCNd2lUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
DSt2mcNn4rhAL+JFr56o4T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
x0YVztz/zbIkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RlLwD1NhPx3iBl
J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
vLY9r60wYSvmZhNqBUrj7lyCtXMIu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
+TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dEIkza8ky5moIwUqYdsx0NxHgRRhORT
8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enCIvGCSx+X3l5SiWg0A
R57hJglezIiVjv3aGwHwvlZvtszK6zV6oXFAu0ECgYAbjo46T4hyP5tJi93V5HDi
Ttiek7xRVxUl+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
R8VdwSk8r9FGLS+9aKcV5PI/WEKlwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
L8ktHMPvodBwNsSBULpG0QKBgBAplTfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
YOdjHdSOoKvDQNWu6ucyLRAWFuISeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
77pBAoGAMmjmIJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY=
-----END RSA PRIVATE KEY-----

closed
bandit16@bandit:~$
```

## Notas adicionales

## Referencias
* https://en.wikipedia.org/wiki/Port_scanner