# Binary Search

## Objetivo
Want to play a game? As you use more of the shell, you might be interested in how they work! Binary search is a classic algorithm used to quickly find an item in a sorted list. Can you find the flag? You'll have 1000 possibilities and only 10 guesses.Cyber security often has a huge amount of data to look through - from logs, vulnerability reports, and forensics. Practicing the fundamentals manually might help you in the future when you have to write your own tools!You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_atlas/17/challenge.zip)

`ssh -p 52158 ctf-player@atlas.picoctf.net`Using the password `f3b61b38`. Accept the fingerprint with `yes`, and `ls` once connected to begin. Remember, in a shell, passwords are hidden!

## Pistas

| No. Pista | Pista                                                                                                                                                                                                  |
| --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 1         | Have you ever played hot or cold? Binary search is a bit like that.                                                                                                                                    |
| 2         | You have a very limited number of guesses. Try larger jumps between numbers!                                                                                                                           |
| 3         | The program will randomly choose a new number each time you connect. You can always try again, but you should start your binary search over from the beginning - try around 500. Can you think of why? |


## Solucion
```bash
──(kali㉿kali)-[~/Documents/parcial1]
└─$ ssh -p 52158 ctf-player@atlas.picoctf.net
ctf-player@atlas.picoctf.net's password: 
Welcome to the Binary Search Game!
I'm thinking of a number between 1 and 1000.
Enter your guess: 500
Lower! Try again.
Enter your guess: 300
Lower! Try again.
Enter your guess: 100
Higher! Try again.
Enter your guess: 200
Higher! Try again.
Enter your guess: 250
Higher! Try again.
Enter your guess: 270
Lower! Try again.
Enter your guess: 260
Higher! Try again.
Enter your guess: 265
Higher! Try again.
Enter your guess: 267
Congratulations! You guessed the correct number: 267
Here's your flag: picoCTF{g00d_gu355_6dcfb67c}
Connection to atlas.picoctf.net closed.
```

## Notas adicionales

## Referencias