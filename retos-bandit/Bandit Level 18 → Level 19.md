# Bandit Level 18 → Level 19

## Objetivo
The password for the next level is stored in a file **readme** in the homedirectory. Unfortunately, someone has modified **.bashrc** to log you out when you log in with SSH.

## Datos de acceso al nivel
```
bandit18
hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
```

## Solucion
```bash
┌──(kali㉿kali)-[~]
└─$ ssh bandit18@bandit.labs.overthewire.org -p 2220 /bin/cat readme         
This is an OverTheWire game server. 
More information on http://www.overthewire.org/wargames

bandit18@bandit.labs.overthewire.orgs password: 
awhqfNnAbc1naukrpqDYcF95h7HoMTrC

```

## Notas adicionales

## Referencias