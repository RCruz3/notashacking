# Bandit Level 32 → Level 33

## Objetivo
There is a git repository at `ssh://bandit31-git@localhost/home/bandit31-git/repo` via the port `2220`. The password for the user `bandit31-git` is the same as for the user `bandit31`.

Clone the repository and find the password for the next level.

## Datos de acceso al nivel
```
bandit31
fb5S2xb7bRyFmAvQYQGEqsbhVyJqhnDy
```

## Solucion
```bash
bandit31@bandit:/tmp/tmp.en6N3eYa81$ git clone ssh://bandit31-git@localhost:2220/home/bandit31-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit31/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit31/.ssh/known_hosts).
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit31-git@localhost's password: 
Permission denied, please try again.
bandit31-git@localhost's password: 
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (4/4), done.
bandit31@bandit:/tmp/tmp.en6N3eYa81$ ls
repo
bandit31@bandit:/tmp/tmp.en6N3eYa81$ cd repo
bandit31@bandit:/tmp/tmp.en6N3eYa81/repo$ ls
README.md
bandit31@bandit:/tmp/tmp.en6N3eYa81/repo$ cat README.md
This time your task is to push a file to the remote repository.

Details:
    File name: key.txt
    Content: 'May I come in?'
    Branch: master

bandit31@bandit:/tmp/tmp.en6N3eYa81/repo$ cat key.txt
cat: key.txt: No such file or directory
bandit31@bandit:/tmp/tmp.en6N3eYa81/repo$ echo 'May I come in?' > key.txt
bandit31@bandit:/tmp/tmp.en6N3eYa81/repo$ ls
key.txt  README.md
bandit31@bandit:/tmp/tmp.en6N3eYa81/repo$ ls. la
Command 'ls.' not found, did you mean:
  command 'lsd' from snap lsd (0.16.0)
  command 'ls' from deb coreutils (9.4-2ubuntu2)
  command 'lsm' from deb lsm (1.0.4-2)
  command 'lsc' from deb livescript (1.6.1+dfsg-3)
  command 'lsd' from deb lsd (0.23.1-8)
  command 'lsh' from deb lsh-client (2.1-14)
  command 'lsw' from deb suckless-tools (47-1)
See 'snap info <snapname>' for additional versions.
bandit31@bandit:/tmp/tmp.en6N3eYa81/repo$ ls -la
total 24
drwxrwxr-x 3 bandit31 bandit31 4096 Nov 28 22:24 .
drwx------ 3 bandit31 bandit31 4096 Nov 28 22:20 ..
drwxrwxr-x 8 bandit31 bandit31 4096 Nov 28 22:20 .git
-rw-rw-r-- 1 bandit31 bandit31    6 Nov 28 22:20 .gitignore
-rw-rw-r-- 1 bandit31 bandit31   15 Nov 28 22:24 key.txt
-rw-rw-r-- 1 bandit31 bandit31  147 Nov 28 22:20 README.md
bandit31@bandit:/tmp/tmp.en6N3eYa81/repo$ cat .gitignore
*.txt
bandit31@bandit:/tmp/tmp.en6N3eYa81/repo$ rm .gitignore
bandit31@bandit:/tmp/tmp.en6N3eYa81/repo$ git add .
bandit31@bandit:/tmp/tmp.en6N3eYa81/repo$ gi commit -m "Agremos el archivo key.txt"
gi: command not found
bandit31@bandit:/tmp/tmp.en6N3eYa81/repo$ git commit -m "Agremos el archivo key.txt"
[master 45b0d35] Agremos el archivo key.txt
 2 files changed, 1 insertion(+), 1 deletion(-)
 delete mode 100644 .gitignore
 create mode 100644 key.txt
bandit31@bandit:/tmp/tmp.en6N3eYa81/repo$ git push origin master
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit31/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit31/.ssh/known_hosts).
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit31-git@localhost's password: 
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 2 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 299 bytes | 299.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
remote: ### Attempting to validate files... ####
remote: 
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote: 
remote: Well done! Here is the password for the next level:
remote: 3O9RfhqyAlVBEZpVb6LYStshZoqoSx5K 
remote: 
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote: 
To ssh://localhost:2220/home/bandit31-git/repo
 ! [remote rejected] master -> master (pre-receive hook declined)
error: failed to push some refs to 'ssh://localhost:2220/home/bandit31-git/repo'
```
3O9RfhqyAlVBEZpVb6LYStshZoqoSx5K
## Notas adicionales



## Referencias