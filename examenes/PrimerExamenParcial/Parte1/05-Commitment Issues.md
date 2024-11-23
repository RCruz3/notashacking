# Commitment Issues
## Objetivo
I accidentally wrote the flag down. Good thing I deleted it! You download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/138/challenge.zip)

## Pistas

| No. Pista | Pista                                                                                                |
| --------- | ---------------------------------------------------------------------------------------------------- |
| 1         | Version control can help you recover files if you change or lose them!                               |
| 2         | Read the chapter on Git from the picoPrimer [here](https://primer.picoctf.org/#_git_version_control) |
| 3         | You can 'checkout' commits to see the files inside them                                              |


## Solucion
```bash
┌──(kali㉿kali)-[~/Documentos/retosPicoPrimerParcial/commitmentIssues]
└─$ cd drop-in         
                                                                            
┌──(kali㉿kali)-[~/Documentos/retosPicoPrimerParcial/commitmentIssues/drop-in]
└─$ ls
message.txt
                                                                            
┌──(kali㉿kali)-[~/Documentos/retosPicoPrimerParcial/commitmentIssues/drop-in]
└─$ git init
Reinicializado el repositorio Git existente en /home/kali/Documentos/retosPicoPrimerParcial/commitmentIssues/drop-in/.git/
                                                                            
┌──(kali㉿kali)-[~/Documentos/retosPicoPrimerParcial/commitmentIssues/drop-in]
└─$ git log 
commit 42942c9c605b30100f5d859ef6e172027447c0db (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:06:23 2024 +0000

    remove sensitive info

commit b562f0b425907789d11d2fe2793e67592dc6be93
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:06:23 2024 +0000

    create flag
                                                                            
┌──(kali㉿kali)-[~/Documentos/retosPicoPrimerParcial/commitmentIssues/drop-in]
└─$ git checkout b562f0b425907789d11d2fe2793e67592dc6be93
Nota: cambiando a 'b562f0b425907789d11d2fe2793e67592dc6be93'.

Te encuentras en estado 'detached HEAD'. Puedes revisar por aquí, hacer
cambios experimentales y hacer commits, y puedes descartar cualquier
commit que hayas hecho en este estado sin impactar a tu rama realizando
otro checkout.

Si quieres crear una nueva rama para mantener los commits que has creado,
puedes hacerlo (ahora o después) usando -c con el comando checkout. Ejemplo:

  git switch -c <nombre-de-nueva-rama>

O deshacer la operación con:

  git switch -

Desactiva este aviso poniendo la variable de config advice.detachedHead en false

HEAD está ahora en b562f0b create flag
                                                                            
┌──(kali㉿kali)-[~/Documentos/retosPicoPrimerParcial/commitmentIssues/drop-in]
└─$ ls
message.txt
                                                                            
┌──(kali㉿kali)-[~/Documentos/retosPicoPrimerParcial/commitmentIssues/drop-in]
└─$ cat message.txt 
picoCTF{s@n1t1z3_c785c319}
```

## Notas adicionales

## Referencias