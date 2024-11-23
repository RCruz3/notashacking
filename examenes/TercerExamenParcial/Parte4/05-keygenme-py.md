# keygenme-py

## Objetivo

[keygenme-trial.py](https://mercury.picoctf.net/static/a6d9cac3bfa4935ceb50c145d3ff5586/keygenme-trial.py)

## Pistas

## Solucion
```bash
──(kali㉿kali)-[~/Documentos/reversing]
└─$ nano keygenme-trial.py.1
                                                                                                                 
┌──(kali㉿kali)-[~/Documentos/reversing]
└─$ nano solucion.py      
                                                                                                                 
┌──(kali㉿kali)-[~/Documentos/reversing]
└─$ python solucion.py   
picoCTF{1n_7h3_|<3y_of_54ef6292}
```
Codigo solucion.py
```bash
import hashlib

key_part_static1_trial = "picoCTF{1n_7h3_|<3y_of_"
#key_part_dynamic1_trial = "xxxxxxxx"
key_part_static2_trial = "}"

temp = hashlib.sha256(b"PRITCHARD").hexdigest()
key_part_dynamic1_trial = temp[4]+temp[5]+temp[3]+temp[6]+temp[2]+temp[7]+temp[1]+temp[8]
key_full_template_trial = key_part_static1_trial+key_part_dynamic1_trial+key_part_static2_trial

print(key_full_template_trial)

```

## Notas adicionales

## Referencias