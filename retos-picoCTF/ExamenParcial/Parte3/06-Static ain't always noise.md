# Static ain't always noise

## Objetivo
Can you look at the data in this binary: [static](https://mercury.picoctf.net/static/bc72945175d643626d6ea9a689672dbd/static)? This [BASH script](https://mercury.picoctf.net/static/bc72945175d643626d6ea9a689672dbd/ltdis.sh) might help!

## Pistas

## Solucion
```bash
┌──(kali㉿kali)-[~]
└─$ wget https://mercury.picoctf.net/static/bc72945175d643626d6ea9a689672dbd/static
--2024-02-28 13:16:55--  https://mercury.picoctf.net/static/bc72945175d643626d6ea9a689672dbd/static
Resolviendo mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Conectando con mercury.picoctf.net (mercury.picoctf.net)[18.189.209.142]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 8376 (8.2K) [application/octet-stream]
Grabando a: «static»

static                100%[=========================>]   8.18K  --.-KB/s    en 0s      

2024-02-28 13:17:03 (16.6 MB/s) - «static» guardado [8376/8376]

                                                                                        
┌──(kali㉿kali)-[~]
└─$ wget https://mercury.picoctf.net/static/bc72945175d643626d6ea9a689672dbd/ltdis.sh
--2024-02-28 13:17:58--  https://mercury.picoctf.net/static/bc72945175d643626d6ea9a689672dbd/ltdis.sh
Resolviendo mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Conectando con mercury.picoctf.net (mercury.picoctf.net)[18.189.209.142]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 785 [application/octet-stream]
Grabando a: «ltdis.sh»

ltdis.sh              100%[=========================>]     785  --.-KB/s    en 0s      

2024-02-28 13:18:06 (2.30 MB/s) - «ltdis.sh» guardado [785/785]

                                                                                        
┌──(kali㉿kali)-[~]
└─$ ls - la
ls: no se puede acceder a '-': No existe el fichero o el directorio
ls: no se puede acceder a 'la': No existe el fichero o el directorio
                                                                                        
┌──(kali㉿kali)-[~]
└─$ la     
.bash_logout      inc_dec.asm                suma_incremento.asm
.bashrc           inc_dec.o                  suma_incremento_decremento
.bashrc.original  inc.o                      suma_incremento_decremento.asm
.cache            incremento                 suma_incremento_decremento.o
.config           incremento.asm             suma_incremento.o
Descargas         incremento.o               .vboxclient-clipboard.pid
Desktop           .java                      .vboxclient-display-svga-x11.pid
.dmrc             .lesshst                   .vboxclient-draganddrop.pid
Documentos        .local                     .vboxclient-seamless.pid
Escritorio        ltdis.sh                   .vboxclient-vmsvga-session-tty7.pid
.face             .mozilla                   .vboxclient-vmsvga-session-tty8.pid
.face.dpkg-new    Música                     Vídeos
.face.icon        .pki                       warm
flag              Plantillas                 .wget-hsts
.gnupg            .profile                   .Xauthority
.ICEauthority     Público                    .xsession-errors
Imágenes          .ssh                       .xsession-errors.old
inc               static                     .zsh_history
inc.asm           .sudo_as_admin_successful  .zshrc
inc_dec           suma_incremento            .zshrc.dpkg-new
                                                                                        
┌──(kali㉿kali)-[~]
└─$ ls     
Descargas   inc.asm         incremento.o     suma_incremento.asm
Desktop     inc_dec         ltdis.sh         suma_incremento_decremento
Documentos  inc_dec.asm     Música           suma_incremento_decremento.asm
Escritorio  inc_dec.o       Plantillas       suma_incremento_decremento.o
flag        inc.o           Público          suma_incremento.o
Imágenes    incremento      static           Vídeos
inc         incremento.asm  suma_incremento  warm
                                                                                        
┌──(kali㉿kali)-[~]
└─$ chmod +x static 
                                                                                        
┌──(kali㉿kali)-[~]
└─$ chmod +x warm  
                                                                                        
┌──(kali㉿kali)-[~]
└─$ strings static | grep pico                      
picoCTF{d15a5m_t34s3r_1e6a7731}

```

## Notas adicionales
* Se usa comando para conceder permisos

## Referencias
