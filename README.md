# ICS3203-CAT2-Assembly--Moriasi-Deogracious-Mosweta-ADM-150196
## Task 1: Control Flow and Conditional Logic 

## Purpose:
This program prompts the user to enter a number. It then classifies the number as either **POSITIVE**, **NEGATIVE**, or **ZERO** based on its value.

## How to Compile and Run:

### 1. **Assembling the Code:**
To compile and assemble the code, use the following commands:

```bash
nasm -f elf32 task1.asm -o task1.o
ld -m elf_i386 -s -o task1 task1.o
```
### 2. **Running the Program:**
After assembling and linking the program, you can run it using the following command:

```bash
./task1
```
## Inputs:
Input a single integer
## Positive Input:
```bash
Enter a number: 5
```
## Negative Input:
```bash
Enter a number: -3
```
## Zero Input:
```bash
Enter a number: 0
```
## Outputs:
## Positive Output:
```bash
The number is positive
```
## Negative Output:
```bash
The number is negative
```
## Zero Output:
```bash
The number is zero
```
### Key Points for **Control Flow and Conditional Logic**:
- **Conditional Jumps**:
  - `je` (Jump if Equal) is used to check if the number is zero after comparing it to `0`.
  - `jl` (Jump if Less) is used to check if the number is negative by comparing it to `0`.
  - If neither condition is met (i.e., the number is positive), the program proceeds to the positive classification.

- **Unconditional Jumps**:
  - The `jmp` instruction is used to skip over the subsequent classification checks after a match is found, ensuring only one classification message is printed.


## Task 2: Array Reversal

## Purpose:
This program prompts the user to enter 5 integers, separated by spaces. It then reverses the order of the integers and outputs the reversed array.

## How to Compile and Run:

### 1. **Assembling the Code:**
To compile and assemble the code, use the following commands:

```bash
nasm -f elf32 task2Array.asm -o task2Array.o
ld -m elf_i386 -s -o task2Array task2Array.o
```
## Input:
Input 5 numbers for example:
```bash
Enter 5 integers separated by space: 5 4 3 2 1
```
## Output:
It outputs:
```bash
The reversed array is: 1 2 3 4 5
```
