# ReadMyCert

## Objetivo
How about we take you on an adventure on exploring certificate signing requestsTake a look at this CSR file [here](https://artifacts.picoctf.net/c/422/readmycert.csr).

## Pistas

| No.  Pista | Pista                                                        |
| ---------- | ------------------------------------------------------------ |
| 1          | Download the certificate signing request and try to read it. |

## Solucion
```bash
┌──(kali㉿kali)-[~/Documentos/crypto/readmycert]
└─$ wget https://artifacts.picoctf.net/c/422/readmycert.csr
--2024-05-16 20:14:30--  https://artifacts.picoctf.net/c/422/readmycert.csr
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.61, 3.161.55.64, 3.161.55.26, ...
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[3.161.55.61]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 997 [application/octet-stream]
Grabando a: «readmycert.csr»

readmycert.csr       100%[====================>]     997  --.-KB/s    en 0s      

2024-05-16 20:14:31 (18.5 MB/s) - «readmycert.csr» guardado [997/997]

                                                                                  
┌──(kali㉿kali)-[~/Documentos/crypto/readmycert]
└─$ file readmycert.csr 
readmycert.csr: PEM certificate request
                                                                                  
┌──(kali㉿kali)-[~/Documentos/crypto/readmycert]
└─$ cat readmycert.csr 
-----BEGIN CERTIFICATE REQUEST-----
MIICpzCCAY8CAQAwPDEmMCQGA1UEAwwdcGljb0NURntyZWFkX215Y2VydF8zNzNi
NGFiMH0xEjAQBgNVBCkMCWN0ZlBsYXllcjCCASIwDQYJKoZIhvcNAQEBBQADggEP
ADCCAQoCggEBAKr+AToJg/TVTvfd9XzYR0gC5TOXa2+T24gjE8n7SHqynuo0Zlfy
oCqZHkxLha4QZszow4M+klP9fe1hy90LAU2enQGELrF3OF5SbNIVnPq97qrSHNI7
D9faAdsBqvezCto1MuMrRD35gwhQPga3WobkMdbJdDwuBpem/Tl3ko3Y9sxq2nAF
cmMNPj40GLtCfW55O8Awn2uN5gGZe+Nw2ArU9AYFidPtFZjBovHv7BVJz5XlhRhu
oiBALZES9kgfOyiwZrcJYZCJh9cJz3d+n2roMyAYMM/VZIjl0aZqSdOPeGYzs3GP
p/jFku8KNBn+mjyyw0H1vRnrK1hkNKXrXOcCAwEAAaAmMCQGCSqGSIb3DQEJDjEX
MBUwEwYDVR0lBAwwCgYIKwYBBQUHAwIwDQYJKoZIhvcNAQELBQADggEBAG0c6ed5
a5zHU5IeI1KBvhGa+zGlrbm4lGQnGoI8wwlr6VN6v07/BGpwWfhjJatAOQ3txT5O
xDrM5A8caxpgGUXmat+C/9XCSQgRA+JckSk3rd6Wz7rYRuKsnycHzVIwyvIgSdjM
5/RKRdYHyFqYHPo9Tf1fThbV0tyQ+kr0tmsO6ZuaKgyDSxtky4U51XzSByKygHOT
Oi+VkzWvn74aOgbelBFMz+3vxaRHW85pe93jN6Gvc+HwYzUFja/SZXaN95sNRhcq
20SbOmg4r2pHUg0Lfs/0EHqDSg6JtKItqZmQUNhUQ7jmL6PtUpQQlkwlfMmEijRn
vlIEqBAkSbo63XQ=
-----END CERTIFICATE REQUEST-----

* Copiamos la llave y la pegamos en la siguiente pagina: https://www.sslshopper.com/csr-decoder.html, abajo nos mostrara la bandera: 
* **CSR Information:**

##### **Common Name:** picoCTF{read_mycert_373b4ab0}

##### **Key Size:** 2048 bit
```

## Notas adicionales

## Referencias