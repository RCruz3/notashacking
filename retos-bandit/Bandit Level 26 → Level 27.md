# Bandit Level 26→ Level 27

## Objetivo
Good job getting a shell! Now hurry and grab the password for bandit27!

## Datos de acceso al nivel
```
bandit26
s0773xxkk0MXfdqOfPRVr9L3jJBUOgCZ
```

## Solucion
```bash
bandit26@bandit:~$ ls
bandit27-do text.txt
bandit26@bandit:~$ ./bandit27-do id
uid=11026(bandit26) gid=11026(bandit26) euid=11027(bandit27) groups=11026(bandit26)
bandit26@bandit:~$ ./bandit27-do cat /etc/bandit_pass/bandit27
YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS
bandit26@bandit:~$
bandit26@bandit:~$ exit
```

## Notas adicionales



## Referencias