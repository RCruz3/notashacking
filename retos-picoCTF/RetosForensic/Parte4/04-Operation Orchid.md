# Operation Orchid

## Objetivo
Download this disk image and find the flag.Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download compressed disk image](https://artifacts.picoctf.net/c/212/disk.flag.img.gz)

## Pistas

## Solucion
```bash
┌──(kali㉿kali)-[/tmp/OpOrchid]
└─$ gzip -d disk.flag.img.gz
                                                           
┌──(kali㉿kali)-[/tmp/OpOrchid]
└─$ fls -o 000411648 disk.flag.img 472
r/r 1875:       .ash_history
r/r * 1876(realloc):    flag.txt
r/r 1782:       flag.txt.enc
                                                           
┌──(kali㉿kali)-[/tmp/OpOrchid]
└─$ icat -o 000411648 disk.flag.img 1782 > flag.txt.enc
                                                           
┌──(kali㉿kali)-[/tmp/OpOrchid]
└─$ icat -o 0000411648 disk.flag.img 1875
touch flag.txt
nano flag.txt 
apk get nano
apk --help
apk add nano
nano flag.txt 
openssl
openssl aes256 -salt -in flag.txt -out flag.txt.enc -k unbreakablepassword1234567
shred -u flag.txt
ls -al
halt
                                                           
┌──(kali㉿kali)-[/tmp/OpOrchid]
└─$ openssl aes256 -salt -d in flag.txt.enc -out flag.txt -k unbreakablepassword1234567
aes256: Use -help for summary.
                                                           
┌──(kali㉿kali)-[/tmp/OpOrchid]
└─$ openssl aes256 -salt -d -in flag.txt.enc -out flag.txt -k unbreakablepassword1234567
*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
bad decrypt
4007B220017F0000:error:1C800064:Provider routines:ossl_cipher_unpadblock:bad decrypt:../providers/implementations/ciphers/ciphercommon_block.c:124:
                                                           
┌──(kali㉿kali)-[/tmp/OpOrchid]
└─$ cat flag.txt                                  
picoCTF{h4un71ng_p457_0a710765}
```

## Notas adicionales

## Referencias