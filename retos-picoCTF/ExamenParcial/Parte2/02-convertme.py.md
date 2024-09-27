# convertme.py

## Objetivo
Run the Python script and convert the given number from decimal to binary to get the flag.[Download Python script](https://artifacts.picoctf.net/c/24/convertme.py)

## Pistas

| No. Pista | Pista                                                                                                                                                                                                        |
| --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 1         | Look up a decimal to binary number conversion app on the web or use your computer's calculator!                                                                                                              |
| 2         | The `str_xor` function does not need to be reverse engineered for this challenge.                                                                                                                            |
| 3         | If you have Python on your computer, you can download the script normally and run it. Otherwise, use the `wget` command in the webshell.                                                                     |
| 4         | To use `wget` in the webshell, first right click on the download link and select 'Copy Link' or 'Copy Link Address'                                                                                          |
| 5         | Type everything after the dollar sign in the webshell: `$ wget` , then paste the link after the space after `wget` and press enter. This will download the script for you in the webshell so you can run it! |
| 6         | Finally, to run the script, type everything after the dollar sign and then press enter: `$ python3 convertme.py`                                                                                             |


## Solucion
```bash
──(kali㉿kali)-[~/Descargas]
└─$ python3 convertme.py
If 44 is in decimal base, what is it in binary base?
Answer: 101100
That is correct! Here's your flag: picoCTF{4ll_y0ur_b4535_722f6b39}

```

## Notas adicionales

## Referencias