# Super SSH

## Objetivo
Using a Secure Shell (SSH) is going to be pretty important. Can you `ssh` as `ctf-player` to `titan.picoctf.net` at port `49566` to get the flag? You'll also need the password `1db87a14`. If asked, accept the fingerprint with `yes`. If your device doesn't have a shell, you can use: [https://webshell.picoctf.org](https://webshell.picoctf.org/) If you're not sure what a shell is, check out our Primer: [https://primer.picoctf.com/#_the_shell](https://primer.picoctf.com/#_the_shell)

## Pistas

| No. Pista | Pista                                                               |
| --------- | ------------------------------------------------------------------- |
| 1         | [https://linux.die.net/man/1/ssh](https://linux.die.net/man/1/ssh)  |
| 2         | You can try logging in 'as' someone with `<user>`@titan.picoctf.net |
| 3         | How could you specify the port?                                     |
| 4         | Remember, passwords are hidden when typed into the shell            |


## Solucion
```bash
──(kali㉿kali)-[~]
└─$ ssh ctf-player@titan.picoctf.net -p 49566
ctf-player@titan.picoctf.net's password: 
Welcome ctf-player, here's your flag: picoCTF{s3cur3_c0nn3ct10n_45a48857}
Connection to titan.picoctf.net closed.
```

## Notas adicionales
* Para especificar el usuario en ssh se usa la sintaxis "ssh [username]@[host]"

## Referencias
* https://linux.die.net/man/1/ssh