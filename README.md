## ICS3203-CAT2-Assembly--Moriasi-Deogracious-Mosweta-ADM-150196
# Task 2: Array Reversal

## Purpose:
This program prompts the user to enter 5 integers, separated by spaces. It then reverses the order of the integers and outputs the reversed array.

## How to Compile and Run:

### 1. **Assembling the Code:**
To compile and assemble the code, use the following commands:

```bash
nasm -f elf32 task2Array.asm -o task2Array.o
ld -m elf_i386 -s -o task2Array task2Array.o
