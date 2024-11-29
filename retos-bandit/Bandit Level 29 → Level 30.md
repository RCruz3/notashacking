# Bandit Level 29 → Level 30

## Objetivo
There is a git repository at `ssh://bandit29-git@localhost/home/bandit29-git/repo` via the port `2220`. The password for the user `bandit29-git` is the same as for the user `bandit29`.

Clone the repository and find the password for the next level.

## Datos de acceso al nivel
```
bandit29
4pT1t5DENaYuqnqvadYs1oE4QLCdjmJ7
```

## Solucion
```bash
bandit29@bandit:/tmp/tmp.vCmtZMDndB$ git clone ssh://bandit29-git@localhost:2220/home/bandit29-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit29/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit29/.ssh/known_hosts).
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit29-git@localhost's password: 
remote: Enumerating objects: 16, done.
remote: Counting objects: 100% (16/16), done.
remote: Compressing objects: 100% (11/11), done.
remote: Total 16 (delta 2), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (16/16), done.
Resolving deltas: 100% (2/2), done.
bandit29@bandit:/tmp/tmp.vCmtZMDndB$ ls
repo
bandit29@bandit:/tmp/tmp.vCmtZMDndB$ cd repo
bandit29@bandit:/tmp/tmp.vCmtZMDndB/repo$ ls
README.md
bandit29@bandit:/tmp/tmp.vCmtZMDndB/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: <no passwords in production!>

bandit29@bandit:/tmp/tmp.vCmtZMDndB/repo$ git log
commit 6ac7796430c0f39290a0e29a4d32e5126544b022 (HEAD -> master, origin/master, origin/HEAD)
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Sep 19 07:08:41 2024 +0000

    fix username

commit e65a928cca4db1863b478cf5e93d1d5b1c1bd6b2
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Sep 19 07:08:41 2024 +0000

    initial commit of README.md
bandit29@bandit:/tmp/tmp.vCmtZMDndB/repo$ git show 6ac7796430c0f39290a0e29a4d32e5126544b022
commit 6ac7796430c0f39290a0e29a4d32e5126544b022 (HEAD -> master, origin/master, origin/HEAD)
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Sep 19 07:08:41 2024 +0000

    fix username

diff --git a/README.md b/README.md
index 2da2f39..1af21d3 100644
--- a/README.md
+++ b/README.md
@@ -3,6 +3,6 @@ Some notes for bandit30 of bandit.
 
 ## credentials
 
-- username: bandit29
+- username: bandit30
 - password: <no passwords in production!>
 
bandit29@bandit:/tmp/tmp.vCmtZMDndB/repo$ git log -p
commit 6ac7796430c0f39290a0e29a4d32e5126544b022 (HEAD -> master, origin/master, origin/HEAD)
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Sep 19 07:08:41 2024 +0000

    fix username

diff --git a/README.md b/README.md
index 2da2f39..1af21d3 100644
--- a/README.md
+++ b/README.md
@@ -3,6 +3,6 @@ Some notes for bandit30 of bandit.
 
 ## credentials
 
-- username: bandit29
+- username: bandit30
 - password: <no passwords in production!>
 

commit e65a928cca4db1863b478cf5e93d1d5b1c1bd6b2
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Sep 19 07:08:41 2024 +0000

    initial commit of README.md

diff --git a/README.md b/README.md
new file mode 100644
index 0000000..2da2f39
--- /dev/null
+++ b/README.md
bandit29@bandit:/tmp/tmp.vCmtZMDndB/repo$ git checkout remotes/origin/dev
Note: switching to 'remotes/origin/dev'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 081ac38 add data needed for development
bandit29@bandit:/tmp/tmp.vCmtZMDndB/repo$ ls -la
total 20
drwxrwxr-x 4 bandit29 bandit29 4096 Nov 28 22:02 .
drwx------ 3 bandit29 bandit29 4096 Nov 28 21:52 ..
drwxrwxr-x 2 bandit29 bandit29 4096 Nov 28 22:02 code
drwxrwxr-x 8 bandit29 bandit29 4096 Nov 28 22:02 .git
-rw-rw-r-- 1 bandit29 bandit29  134 Nov 28 22:02 README.md
bandit29@bandit:/tmp/tmp.vCmtZMDndB/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: qp30ex3VLz5MDG1n91YowTv4Q8l7CDZL

```
qp30ex3VLz5MDG1n91YowTv4Q8l7CDZL
## Notas adicionales



## Referencias