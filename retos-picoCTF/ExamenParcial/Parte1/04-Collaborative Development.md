# Collaborative Development

## Objetivo
#### Description

My team has been working very hard on new features for our flag printing program! I wonder how they'll work together? You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/178/challenge.zip)
## Pistas

| No. Pista | Pista                                                                             |
| --------- | --------------------------------------------------------------------------------- |
| 1         | `git branch -a` will let you see available branches                               |
| 2         | How can file 'diffs' be brought to the main branch? Don't forget to `git config`! |
| 3         | Merge conflicts can be tricky! Try a text editor like nano, emacs, or vim.        |

## Solucion
```bash
┌──(kali㉿kali)-[~/Documentos/retosPicoPrimerParcial/collaborativeDevelopment/drop-in]
└─$ git init               
Reinicializado el repositorio Git existente en /home/kali/Documentos/retosPicoPrimerParcial/collaborativeDevelopment/drop-in/.git/
                                                                                             
┌──(kali㉿kali)-[~/Documentos/retosPicoPrimerParcial/collaborativeDevelopment/drop-in]
└─$ git branch -a
  feature/part-1
  feature/part-2
  feature/part-3
* main
                                                                                             
┌──(kali㉿kali)-[~/Documentos/retosPicoPrimerParcial/collaborativeDevelopment/drop-in]
└─$ git checkout feature/part-1                          
Cambiado a rama 'feature/part-1'
                                                                                             
┌──(kali㉿kali)-[~/Documentos/retosPicoPrimerParcial/collaborativeDevelopment/drop-in]
└─$ ls    
flag.py
                                                                                             
┌──(kali㉿kali)-[~/Documentos/retosPicoPrimerParcial/collaborativeDevelopment/drop-in]
└─$ python flag.py
Printing the flag...
picoCTF{t3@mw0rk_                                                                                             
┌──(kali㉿kali)-[~/Documentos/retosPicoPrimerParcial/collaborativeDevelopment/drop-in]
└─$ ls
flag.py
                                                                                             
┌──(kali㉿kali)-[~/Documentos/retosPicoPrimerParcial/collaborativeDevelopment/drop-in]
└─$ git checkout feature/part-2
Cambiado a rama 'feature/part-2'
                                                                                             
┌──(kali㉿kali)-[~/Documentos/retosPicoPrimerParcial/collaborativeDevelopment/drop-in]
└─$ ls
flag.py
                                                                                             
┌──(kali㉿kali)-[~/Documentos/retosPicoPrimerParcial/collaborativeDevelopment/drop-in]
└─$ python flag.py             
Printing the flag...
m@k3s_th3_dr3@m_                                                                                             
┌──(kali㉿kali)-[~/Documentos/retosPicoPrimerParcial/collaborativeDevelopment/drop-in]
└─$ git checkout feature/part-3
Cambiado a rama 'feature/part-3'
                                                                                             
┌──(kali㉿kali)-[~/Documentos/retosPicoPrimerParcial/collaborativeDevelopment/drop-in]
└─$ ls                         
flag.py
                                                                                             
┌──(kali㉿kali)-[~/Documentos/retosPicoPrimerParcial/collaborativeDevelopment/drop-in]
└─$ python flag.py             
Printing the flag...
w0rk_6c06cec1}
```

## Notas adicionales

## Referencias