# binhexa

## Objetivo
How well can you perfom basic binary operations?Start searching for the flag here `nc titan.picoctf.net 61694`

## Pistas

| No. Pista | Pista |
| --------- | ----- |
|           |       |


## Solucion
```bash
┌──(kali㉿kali)-[~/Documents/parcial1]
└─$ nc titan.picoctf.net 61694

Welcome to the Binary Challenge!"
Your task is to perform the unique operations in the given order and find the final result in hexadecimal that yields the flag.

Binary Number 1: 01010101
Binary Number 2: 00101010


Question 1/6:
Operation 1: '|'
Perform the operation on Binary Number 1&2.
Enter the binary result: 0b1111111
Correct!

Question 2/6:
Operation 2: '&'
Perform the operation on Binary Number 1&2.
Enter the binary result: 0b0
Correct!

Question 3/6:
Operation 3: '*'
Perform the operation on Binary Number 1&2.
Enter the binary result: 0b110111110010
Correct!

Question 4/6:
Operation 4: '<<'
Perform a left shift of Binary Number 1 by 1 bits.
Enter the binary result: 0b10101010
Correct!

Question 5/6:
Operation 5: '>>'
Perform a right shift of Binary Number 2 by 1 bits .
Enter the binary result: 0b10101
Correct!

Question 6/6:
Operation 6: '+'
Perform the operation on Binary Number 1&2.
Enter the binary result: 0b1111111
Correct!

Enter the results of the last operation in hexadecimal: 0x7f

Correct answer!
The flag is: picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_6862762d}
```
Codigo .py
```bash
def bin_operations(a, b, operation):
    if operation == '+':
        result = bin(a + b)
    elif operation == '-':
        result = bin(a - b)
    elif operation == '*':
        result = bin(a * b)
    elif operation == '>>':
        num = input("Choose number a or b: ")
        if num == 'a':
            result = bin(a >> 1)
        elif num == 'b':
            result = bin(b >> 1)
        else:
            print("Invalid number to choose")
            return None
    elif operation == '<<':
        num = input("Choose number a or b: ")
        if num == 'a':
            result = bin(a << 1)
        elif num == 'b':
            result = bin(b << 1)
        else:
            print("Invalid number to choose")
            return None
    elif operation == '&':
        result = bin(a & b)
    elif operation == '|':
        result = bin(a | b)
    else:
        print("Invalid operation")
        return None
    return result

if __name__ == "__main__":
    a = input("Input number a: ")
    b = input("Input number b: ")
    a = int(a, 2)
    b = int(b, 2)
    for i in range(6):
        operation = input("Choose the binary operation: ")
        result = bin_operations(a, b, operation)
        if result:
            print("Binary result: ", result)
        if i == 5:
            print(f"Hexadecimal result: {hex(int(result, 2))}")
```

## Notas adicionales

## Referencias