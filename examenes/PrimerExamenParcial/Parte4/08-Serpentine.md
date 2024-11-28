# Serpentine

## Objetivo
Find the flag in the Python script![Download Python script](https://artifacts.picoctf.net/c/35/serpentine.py)

## Pistas

| No. Pista | Pista                                                                             |
| --------- | --------------------------------------------------------------------------------- |
| 1         | Try running the script and see what happens                                       |
| 2         | In the webshell, try examining the script with a text editor like `nano`          |
| 3         | To exit `nano`, press Ctrl and x and follow the on-screen prompts                 |
| 4         | The `str_xor` function does not need to be reverse engineered for this challenge. |


## Solucion
```bash
┌──(kali㉿kali)-[~/Documents/parcial1]
└─$ nano serpentine.py   
                                                           
┌──(kali㉿kali)-[~/Documents/parcial1]
└─$ python3 serpentine.py

    Y
  .-^-.
 /     \      .- ~ ~ -.
()     ()    /   _ _   `.                     _ _ _
 \_   _/    /  /     \   \                . ~  _ _  ~ .
   | |     /  /       \   \             .' .~       ~-. `.
   | |    /  /         )   )           /  /             `.`.
   \ \_ _/  /         /   /           /  /                `'
    \_ _ _.'         /   /           (  (
                    /   /             \                     /   /               \                    /   /                 )  )
                 (   (                 /  /
                  `.  `.             .'  /
                    `.   ~ - - - - ~   .'
                       ~ . _ _ _ _ . ~

Welcome to the serpentine encourager!


a) Print encouragement
b) Print flag
c) Quit

What would you like to do? (a/b/c) a

-----------------------------------------------------
Look how far you've come!
-----------------------------------------------------


a) Print encouragement
b) Print flag
c) Quit

What would you like to do? (a/b/c) b
picoCTF{7h3_r04d_l355_7r4v3l3d_ae0b80bd}
```

## Notas adicionales

## Referencias