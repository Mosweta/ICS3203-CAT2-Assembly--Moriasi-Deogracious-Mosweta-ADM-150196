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
---

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
### 2. **Running the Program:**
After assembling and linking the program, you can run it using the following command:

```bash
./task2Array
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
## Task 3: Modular Program with Subroutines for Factorial Calculation 

## Purpose:

This program calculates the factorial of a user-input number between 1 and 10 using assembly language. It validates the input, computes the factorial recursively, and outputs the result.

## How to Compile and Run:

### 1. **Assembling the Code:**
To compile and assemble the code, use the following commands:

```bash
nasm -f elf32 task3Factorial.asm -o task3Factorial.o
ld -m elf_i386 -s -o task3Factorial task3Factorial.o
```
---
### 2. **Running the Program:**
After assembling and linking the program, you can run it using the following command:

```bash
./task3Factorial
```
## Input:
Enter any number between 1 and 10 for example:
```bash
Enter a number (1-10): 5
```
## Output:
The program calculates the factorial of the input number and outputs.
It outputs:
```bash
The factorial of the number is: 120
```
###Insights
### **1. Input Handling**
- The program prompts the user to enter a number between `1` and `10`.
- The input is read from the console, converted from ASCII to an integer, and stored in the `input_num` memory location.

### **2. Input Validation**
- The program ensures the input is valid:
  - If `input_num` is less than `1` or greater than `10`, an error message is displayed, and the program exits.

### **3. Factorial Calculation**
- The factorial of the input number is calculated using recursion:
  - **Base Case**: If `eax` equals `1`, the function returns `1`.
  - **Recursive Case**:
    1. The current value of `eax` is saved onto the stack using `push`.
    2. The program decrements `eax` and recursively calls the factorial function.
    3. The saved value is restored using `pop`, and the result of the recursive call is multiplied by the saved value.

### **4. Number-to-String Conversion**
- The calculated factorial (stored in `eax`) is converted to a string:
  1. The remainder of dividing `eax` by `10` is computed using `div` and stored in `edx`.
  2. The remainder is converted to an ASCII character and stored in the buffer.
  3. The process repeats until `eax` becomes `0`.

### **5. Status Messages**
- The program displays appropriate messages during execution:
  - If the input is valid, the factorial result is displayed.
  - If the input is invalid, an error message prompts the user to enter a number between `1` and `10`.

---

## **Flow of Execution**
1. **Prompt User**: The program asks the user to enter a number between `1` and `10`.
2. **Read Input**: The input is read and converted to an integer.
3. **Validate Input**: The program checks if the input is within the valid range:
   - If valid, it proceeds to calculate the factorial.
   - If invalid, it displays an error message and exits.
4. **Calculate Factorial**:
   - Uses a recursive function, saving and restoring values using the stack.
5. **Convert Result to String**:
   - Converts the factorial result from an integer to a string for display.
6. **Display Result**: The program outputs the calculated factorial.
7. **Exit**: The program terminates gracefully.

---

---
## Task 4: Data Monitoring and Control Using Port-Based Simulation 

## Purpose:
### Water Level Control System:
This program simulates a water level control system using assembly language. It prompts the user to input a water level (integer between 0 and 100), processes the input, and performs the following actions based on the level:

.Turns the motor ON or OFF.
.Activates or deactivates an alarm. The program outputs the motor and alarm statuses based on the water level.


## How to Compile and Run:

### 1. **Assembling the Code:**
To compile and assemble the code, use the following commands:

```bash
 nasm -f elf32 task4Control.asm -o task4Control.o
 ld -m elf_i386 -s -o task4Control task4Control.o
```
### 2. **Running the Program:**
After assembling and linking the program, you can run it using the following command:

```bash
./task2Array
```
## Low Input:
Input low water level e.g(< 30) for example:
```bash
Enter water level (0-100): 29
```
## Output:
It outputs:
```bash
Motor ON Alarm OFF
```
## Moderate Input:
Input moderate water level e.g(30 to 90 ) for example:
```bash
Enter water level (0-100): 40
```
## Output:
It outputs:
```bash
Motor ON Alarm ON
```
## High Input:
Input moderate water level e.g(30 to 90 ) for example:
```bash
Enter water level (0-100): 91
```
## Output:
It outputs:
```bash
Motor OFF Alarm ON
```

## how the program determines which action to take based on the “sensor” input and how memory locations or ports are manipulated to reflect the motor or alarm status.
## **How the Program Works**

### **1. Input Handling**
- The program prompts the user to enter a water level (0–100).
- The input is converted from ASCII to an integer and stored in the `sensor_value` memory location.

### **2. Decision Logic**
- The program determines the motor and alarm actions based on the value of `sensor_value`:
  1. **Low Water Level (`sensor_value < 30`)**:
     - Motor is turned ON (`motor_status = 1`).
     - Alarm remains OFF (`alarm_status = 0`).
  2. **Moderate Water Level (`30 <= sensor_value <= 90`)**:
     - Motor remains ON (`motor_status = 1`).
     - Alarm is turned ON (`alarm_status = 1`).
  3. **High Water Level (`sensor_value > 90`)**:
     - Motor is turned OFF (`motor_status = 0`).
     - Alarm is turned ON (`alarm_status = 1`).

### **3. Memory Locations**
The program uses the following memory locations:
- **`sensor_value` (2 bytes)**: Stores the water level input for decision-making.
- **`motor_status` (1 byte)**: Stores the motor status:
  - `0`: Motor OFF
  - `1`: Motor ON
- **`alarm_status` (1 byte)**: Stores the alarm status:
  - `0`: Alarm OFF
  - `1`: Alarm ON

### **4. Status Display**
- The program outputs the current motor and alarm statuses to the console:
  - Motor Status:
    - `Motor ON` if `motor_status = 1`.
    - `Motor OFF` if `motor_status = 0`.
  - Alarm Status:
    - `Alarm ON` if `alarm_status = 1`.
    - `Alarm OFF` if `alarm_status = 0`.

---

## **Flow of Execution**
1. **Prompt User**: The program prompts the user to input the water level.
2. **Process Input**: The input is converted to an integer and stored in `sensor_value`.
3. **Evaluate Conditions**: 
   - Compare `sensor_value` against thresholds (`30` and `90`) to decide actions.
4. **Update Status**:
   - Modify `motor_status` and `alarm_status` in memory.
5. **Display Status**:
   - Print the motor and alarm statuses to the console.

---
