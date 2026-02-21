# Arithmetic-operation-using-8086
# 8086 Assembly Language Programs for Arithmetic Operations

## AIM

To write and execute Assembly Language Programs to perform arithmetic operations for the 8086 microprocessor.

---

## APPARATUS REQUIRED

* Personal Computer with MASM Software

---

## 1. ADDITION

#### Algorithm

1. Initialize memory location in HL register.
2. Store 1st data.
3. Increment HL to enter 2nd data.
4. Move 2nd number to accumulator.
5. Decrement HL.
6. Add value in memory with accumulator.
7. Store result.
8. Stop.


## FLOW CHART
<img width="707" height="1024" alt="image" src="https://github.com/user-attachments/assets/b5a7062d-e294-47cd-9683-a40de25e82de" />


#### Program

```asm
CODE SEGMENT
ASSUME CS:CODE, DS:CODE
ORG 1000H
MOV CL,00H
MOV AX,1234H
MOV BX,1234H
ADD AX,BX
JNC L1
INC CL
L1:MOV SI,1200H
MOV [SI],AX
MOV [SI+2],CL
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|   1200      :    12     |   1204         :    24   |
|   1201      :    34     |   1205         :    68   |
|   1202      :    12     |   1206         :    00   |
|   1203      :    34     |                          |


#### Manual Calculations

<img width="1378" height="1057" alt="545436153-01c09a3f-c20c-40e5-b1f6-0911332b26d8" src="https://github.com/user-attachments/assets/2f4dee3f-cd01-4106-96cf-0dc515fe2c5b" />

---

## OUTPUT IMAGE FROM MASM SOFTWARE

<img width="642" height="433" alt="image" src="https://github.com/user-attachments/assets/c97ffd85-4b51-4973-9831-656169887928" />


## 2. SUBTRACTION

#### Algorithm

1. Initialize memory and store 1st data.
2. Increment to get 2nd data.
3. Move 2nd data to accumulator.
4. Subtract memory content.
5. Store result.

## FLOWCHART

<img width="578" height="797" alt="image" src="https://github.com/user-attachments/assets/564c3c7a-33ce-4a1c-8920-beb5c24b9b47" />


#### Program
```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV CL,00H
MOV AX,[SI]
MOV BX,[SI+02H]
SUB AX,BX
JNC L1
INC CL
L1:
MOV [SI+04H],AX
MOV [SI+06H],CL
MOV AH,4CH
INT 21H
CODE ENDS
END
```


#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|   1200      :    67     |   1204         :    55   |
|   1201      :    45     |   1205         :    11   |
|   1202      :    12     |   1206         :    00   |
|   1203      :    34     |                          |

#### Manual Calculations

<img width="1600" height="900" alt="545439937-54950607-903a-4a72-9f58-aa7243029edf" src="https://github.com/user-attachments/assets/46ac8808-333a-491f-8f57-ce54f616023a" />

---


## OUTPUT SCREEN FROM MASM SOFTWARE

## 3. MULTIPLICATION

#### Algorithm

1. Initialize memory and store operands.
2. Move operands to registers.
3. Multiply.
4. Store result.

##FLOWCHART

<img width="569" height="906" alt="image" src="https://github.com/user-attachments/assets/88be88ff-2896-4a88-b73d-84ccffd2fcf9" />



#### Program

```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV DX,0000H
MOV AX,[SI]
MOV BX,[SI+02H]
MUL BX
MOV [SI+04H],AX
MOV [SI+06H],DX
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|   1200      :    12     |   1204         :    44   |
|   1201      :    34     |   1205         :    51   |
|   1202      :    12     |   1206         :    97   |
|   1203      :    34     |   1207         :    0A   |

#### Manual Calculations

<img width="1559" height="1047" alt="545440298-8cfcb9c0-2aa5-4551-baf4-46a966635f8f" src="https://github.com/user-attachments/assets/293ceaa4-fd39-4864-a73b-72c1f33b2785" />

---
## OUTPUT SCREEN FROM MASM SOFTWARE

![WhatsApp Image 2026-02-05 at 11 46 31 AM](https://github.com/user-attachments/assets/196f27fb-9718-4ebe-b0ec-be4cef87295d)

## 4. DIVISION

#### Algorithm

1. Load memory location of operands.
2. Perform division.
3. Store result.

   ## FLOWCHART
<img width="1065" height="802" alt="image" src="https://github.com/user-attachments/assets/25b4a483-0d42-494b-8639-1af3ea17191b" />


#### Program

```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV DX,0000H
MOV AX,[SI]
MOV BX,[SI+02H]
DIV BX
MOV [SI+04H],AX
MOV [SI+06H],DX
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|   1200      :    12     |   1204         :    01   |
|   1201      :    34     |   1205         :    00   |
|   1202      :    12     |   1206         :    00   |
|   1203      :    34     |   1207         :    00   |

#### Manual Calculations


![545441026-f4734393-d10f-46c9-971c-39eb6b3ec5a6](https://github.com/user-attachments/assets/0557be01-08ce-4364-8056-64a56788da9c)

---

## OUTPUT FROM MASM SOFTWARE

<img width="642" height="433" alt="image" src="https://github.com/user-attachments/assets/438fa20c-9d37-4d39-bb78-6a8352bf6ced" />


## RESULT

Thus, the Assembly Language Programs for 8086 to perform arithmetic operations (Addition, Subtraction, Multiplication, and Division) using both direct and indirect methods were successfully written and executed using MASM.

