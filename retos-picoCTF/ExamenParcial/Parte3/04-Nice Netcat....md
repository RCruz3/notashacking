# Nice Netcat

## Objetivo
There is a nice program that you can talk to by using this command in a shell: `$ nc mercury.picoctf.net 43239`, but it doesn't speak English...

## Pistas
| No. Pista | Pista                                                                                                                                 |
| --------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| 1         | You can practice using netcat with this picoGym problem: [what's a netcat?](https://play.picoctf.org/practice/challenge/34)           |
| 2         | You can practice reading and writing ASCII with this picoGym problem: [Let's Warm Up](https://play.picoctf.org/practice/challenge/22) |

## Solucion
```bash
──(kali㉿kali)-[~]
└─$ nc mercury.picoctf.net 43239
112 
105 
99 
111 
67 
84 
70 
123 
103 
48 
48 
100 
95 
107 
49 
116 
116 
121 
33 
95 
110 
49 
99 
51 
95 
107 
49 
116 
116 
121 
33 
95 
55 
99 
48 
56 
50 
49 
102 
53 
125 
10 
```

## Notas adicionales
* Convertir de decimal a ASCII

## Referencias
https://bfotool.com/es/decimal-to-ascii