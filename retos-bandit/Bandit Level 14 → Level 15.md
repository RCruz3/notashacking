# Bandit Level 14 → Level 15

## Objetivo
The password for the next level can be retrieved by submitting the password of the current level to **port 30000 on localhost**.

## Datos de acceso al nivel
```
bandit14
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
```

## Solucion
```bash
bandit14@bandit:~$ nc localhost 30000
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
Correct!
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

^C
bandit14@bandit:~$ 
```

## Notas adicionales

## Referencias
* https://www.youtube.com/watch?v=7_LPdttKXPc
* http://computer.howstuffworks.com/web-server5.htm
* https://en.wikipedia.org/wiki/IP_address
* https://en.wikipedia.org/wiki/Localhost
* http://computer.howstuffworks.com/web-server8.htm
* https://en.wikipedia.org/wiki/Port_(computer_networking)