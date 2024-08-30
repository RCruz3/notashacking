# Bandit Level 15 → Level 16

## Objetivo
The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL encryption.

**Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…**

## Datos de acceso al nivel
```
bandit15
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
```

## Solucion
```bash
bandit15@bandit:~$ openssl s_client -connect localhost:30001
CONNECTED(00000003)
Cant use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Sep 17 08:03:36 2023 GMT
verify return:1
depth=0 CN = localhost
notAfter=Sep 17 08:03:36 2023 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Sep 17 08:02:36 2023 GMT; NotAfter: Sep 17 08:03:36 2023 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEeW0MujANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjMwOTE3MDgwMjM2WhcNMjMwOTE3MDgwMzM2WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQDE
oRX/H4qjwHCLneK/4xT13Q9kjKLU9+76eFWp5DuqvOU9qDwf6ZRPXyjW1vJ0UrXm
+me1SLmMoRHK+O88QUVxOaDAWePIn2B5QCuCF7gDjbbp51hCgNUvJqb+fn5miibQ
4aZxiBbC3RmpxHL8bzDHRbZtQtENEEbFYkuQP0d1uQjPkwpU3664TW0ssh+aaz8Z
CIKUfVB1IpYCPcAbhKROOpUiaUozW04dgOv0QQfqXB0/3wOe/xW/dhjR1vm5ir1y
CGOPN9n1MmImhFf3cUIRD2wnO6U0SVIUokSOr4Lpwy5j5Zo8u85AxErmQTf4RPsw
yAP0aFprsHvSndaMr+dJAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQCF
GXDOH5ZVmrPsa+5wp/tZQ7tEH9JJ9pVGsBN65YcdbfsjZpW9zhSxJCF8baFmR6ht
1HVJd+jeuNKncs7plLR+7k5wCbzQmwpZquUymKAdSfMFxD5FepKOajSZCe0yu+SK
kcOb4Y/v6lpltmpDI9MGlBW7cY9uy3tLQvoTu2Tq/Y4Kicm+Ass9c5SkhnMMb0wL
q5nNDYfLm6wQesYXw4zOu/QK/A1NTHTGz3uaznytLFmFm3Yv8IVz6C3GDB/DKkAk
cc8Con5QEVy59IC7uosR+6853xpeLomiK/CqgT8gWjVUnw34jEXEO+OPBDVLhMF1
TJk6AxA+iXZOJy1IuThT
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
    Session-ID: 81B2F344CBE231A383CE1DEB7DC98DB2CDE19BFC2230BFABEAD614DFCE41C6C5
    Session-ID-ctx: 
    Resumption PSK: 57C9702E50D15075E6F6A26A90EB6C2BE85B477F89AC69A174007C8CA48A394D6C7B237B00D46971FB442CED4C8CC22F
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - fc 4b 37 d8 7a 5e 3f dd-ff 0a 29 a4 85 99 71 54   .K7.z^?...)...qT
    0010 - f1 c6 0f 8f c3 73 70 8b-79 e3 b8 7d d4 80 05 6d   .....sp.y..}...m
    0020 - c6 ec b0 28 5a d6 cc 2d-8d 06 34 ed e8 ba 25 3a   ...(Z..-..4...%:
    0030 - fa 7a 2a 10 ff 2e b2 5c-1f 83 fd 8f 7b af 7a 64   .z*....\....{.zd
    0040 - e9 ea ec a6 9b 9c 87 43-4e 6b d5 c0 6b 5f 71 ef   .......CNk..k_q.
    0050 - 07 b3 f3 38 da 5d bf 16-24 40 cb dd 6e 5c 67 87   ...8.]..$@..n\g.
    0060 - 7f bf 27 36 93 df ea 70-02 69 fa 26 e6 81 ae 5f   ..'6...p.i.&..._
    0070 - fc 4b 4c 2f 26 4f dc 1b-b4 12 8a 07 28 52 26 4c   .KL/&O......(R&L
    0080 - 19 76 ca 45 9d e0 85 39-e1 5a 0c 0e 25 2a cc 75   .v.E...9.Z..%*.u
    0090 - 2f f5 0e d1 5f 4f 7f a1-2f b8 2b b0 85 e3 93 a0   /..._O../.+.....
    00a0 - d2 b8 2f eb 98 f9 2c 61-c4 8b 28 29 ef 2d 43 d4   ../...,a..().-C.
    00b0 - eb b6 b1 88 a3 89 22 c6-cf b0 0f 2e 43 21 e9 b6   ......".....C!..
    00c0 - ee 1a ed 09 dc dd 1c 27-58 1b cb 60 da 9b 73 f3   .......'X..`..s.

    Start Time: 1695044551
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
    Session-ID: A13BEEC712DC28EEE9B3D2B000AC7760715A18C79DA7A885DC24C754DA2A4C34
    Session-ID-ctx: 
    Resumption PSK: CEA737F09AD1A5D699A83607981B4399162E5F9AF9BD0568C8CEB1802295425C669B5590BCBBD6FFF7EE6588DA0D8369
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - fc 4b 37 d8 7a 5e 3f dd-ff 0a 29 a4 85 99 71 54   .K7.z^?...)...qT
    0010 - a2 54 49 4a 6b 37 80 7e-cf 9d 2f 67 22 df bc b3   .TIJk7.~../g"...
    0020 - 61 0e 5f a5 75 b0 56 d6-cf 3b 12 f1 97 78 9e d1   a._.u.V..;...x..
    0030 - e1 29 6a 0b b5 22 91 77-ce 71 e4 85 dc a1 eb 64   .)j..".w.q.....d
    0040 - 0c bc 6f a3 b4 97 03 e6-09 a4 22 3b 39 00 4a 89   ..o.......";9.J.
    0050 - 18 38 b3 51 37 d2 c7 94-8c 15 55 6d f7 7c b6 48   .8.Q7.....Um.|.H
    0060 - 70 07 96 de 49 3e ea 75-d8 1e ce 47 90 09 bf 41   p...I>.u...G...A
    0070 - 2c ae 4a e3 c8 d0 02 a8-b5 c1 07 e2 df 6e 11 00   ,.J..........n..
    0080 - 5e b1 72 51 dc ce 3c 6f-05 e7 10 e9 b1 86 20 4b   ^.rQ..<o...... K
    0090 - 51 d2 d1 15 d5 5a 96 22-c2 8b 16 bc b3 fa 83 82   Q....Z."........
    00a0 - 44 6f aa 8d 22 9a 24 99-5e 25 01 58 21 66 90 52   Do..".$.^%.X!f.R
    00b0 - 8b 8b db 22 8e 2b 59 9d-37 24 ad f6 d1 81 8a 57   ...".+Y.7$.....W
    00c0 - 40 2c 21 e2 21 73 dd 95-ab ca c8 99 50 42 01 1e   @,!.!s......PB..

    Start Time: 1695044551
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
Correct!
JQttfApK4SeyHwDlI9SXGR50qclOAil1

closed
bandit15@bandit:~$
```

## Notas adicionales

## Referencias