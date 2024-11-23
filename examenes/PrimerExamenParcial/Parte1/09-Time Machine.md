# Time Machine

## Objetivo
What was I last working on? I remember writing a note to help me remember... You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/162/challenge.zip)

## Pistas

| No. Pista | Pista                                                                                                 |
| --------- | ----------------------------------------------------------------------------------------------------- |
| 1         | The `cat` command will let you read a file, but that won't help you here!                             |
| 2         | Read the chapter on Git from the picoPrimer [here](https://primer.picoctf.org/#_git_version_control). |
| 3         | When committing a file with git, a message can (and should) be included.                              |


## Solucion
```bash
┌──(kali㉿kali)-[~/Documentos/retosPicoPrimerParcial/timeMachine]
└─$ wget https://artifacts.picoctf.net/c_titan/162/challenge.zip
--2024-03-17 23:17:46--  https://artifacts.picoctf.net/c_titan/162/challenge.zip
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 18.154.144.104, 18.154.144.107, 18.154.144.85, ...
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[18.154.144.104]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 17739 (17K) [application/octet-stream]
Grabando a: «challenge.zip»

challenge.zip           100%[============================>]  17.32K  --.-KB/s    en 0.02s   

2024-03-17 23:17:48 (699 KB/s) - «challenge.zip» guardado [17739/17739]

                                                                                             
┌──(kali㉿kali)-[~/Documentos/retosPicoPrimerParcial/timeMachine]
└─$ ls
challenge.zip
                                                                                             
┌──(kali㉿kali)-[~/Documentos/retosPicoPrimerParcial/timeMachine]
└─$ unzip challenge.zip 
Archive:  challenge.zip
   creating: drop-in/
  inflating: drop-in/message.txt     
   creating: drop-in/.git/
   creating: drop-in/.git/branches/
  inflating: drop-in/.git/description  
   creating: drop-in/.git/hooks/
  inflating: drop-in/.git/hooks/applypatch-msg.sample  
  inflating: drop-in/.git/hooks/commit-msg.sample  
  inflating: drop-in/.git/hooks/fsmonitor-watchman.sample  
  inflating: drop-in/.git/hooks/post-update.sample  
  inflating: drop-in/.git/hooks/pre-applypatch.sample  
  inflating: drop-in/.git/hooks/pre-commit.sample  
  inflating: drop-in/.git/hooks/pre-merge-commit.sample  
  inflating: drop-in/.git/hooks/pre-push.sample  
  inflating: drop-in/.git/hooks/pre-rebase.sample  
  inflating: drop-in/.git/hooks/pre-receive.sample  
  inflating: drop-in/.git/hooks/prepare-commit-msg.sample  
  inflating: drop-in/.git/hooks/update.sample  
   creating: drop-in/.git/info/
  inflating: drop-in/.git/info/exclude  
   creating: drop-in/.git/refs/
   creating: drop-in/.git/refs/heads/
 extracting: drop-in/.git/refs/heads/master  
   creating: drop-in/.git/refs/tags/
 extracting: drop-in/.git/HEAD       
  inflating: drop-in/.git/config     
   creating: drop-in/.git/objects/
   creating: drop-in/.git/objects/pack/
   creating: drop-in/.git/objects/info/
   creating: drop-in/.git/objects/43/
 extracting: drop-in/.git/objects/43/246218ab4fc7b30e9a9dff073e012316851469  
   creating: drop-in/.git/objects/25/
 extracting: drop-in/.git/objects/25/16effb8d70e33bdd0023629b164a77225e1ec2  
   creating: drop-in/.git/objects/71/
 extracting: drop-in/.git/objects/71/2314f105348e295f8cadd7d7dc4e9fa871e9a2  
  inflating: drop-in/.git/index      
 extracting: drop-in/.git/COMMIT_EDITMSG  
   creating: drop-in/.git/logs/
  inflating: drop-in/.git/logs/HEAD  
   creating: drop-in/.git/logs/refs/
   creating: drop-in/.git/logs/refs/heads/
  inflating: drop-in/.git/logs/refs/heads/master  
                                                                                             
┌──(kali㉿kali)-[~/Documentos/retosPicoPrimerParcial/timeMachine]
└─$ ls
challenge.zip  drop-in
                                                                                             
┌──(kali㉿kali)-[~/Documentos/retosPicoPrimerParcial/timeMachine]
└─$ cd drop-in    
                                                                                             
┌──(kali㉿kali)-[~/Documentos/retosPicoPrimerParcial/timeMachine/drop-in]
└─$ ls
message.txt
                                                                                             
┌──(kali㉿kali)-[~/Documentos/retosPicoPrimerParcial/timeMachine/drop-in]
└─$ cat message.txt
This is what I was working on, but I'd need to look at my commit history to know why...                                                                                             
┌──(kali㉿kali)-[~/Documentos/retosPicoPrimerParcial/timeMachine/drop-in]
└─$ git init                                             
Reinicializado el repositorio Git existente en /home/kali/Documentos/retosPicoPrimerParcial/timeMachine/drop-in/.git/
                                                                                             
┌──(kali㉿kali)-[~/Documentos/retosPicoPrimerParcial/timeMachine/drop-in]
└─$ cat message.txt
This is what I was working on, but I'd need to look at my commit history to know why...                                                                                             
┌──(kali㉿kali)-[~/Documentos/retosPicoPrimerParcial/timeMachine/drop-in]
└─$ git log                                                     
commit 712314f105348e295f8cadd7d7dc4e9fa871e9a2 (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:26 2024 +0000

    picoCTF{t1m3m@ch1n3_e8c98b3a}
```

## Notas adicionales

## Referencias
* https://primer.picoctf.org/#_git_version_control
