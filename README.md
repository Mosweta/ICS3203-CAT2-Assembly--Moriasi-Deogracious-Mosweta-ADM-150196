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
