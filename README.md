# 8-Bit-Arithmetic-Operations-using-8085
## Aim:
To perform 8-bit arithmetic operations such as addition, subtraction, multiplication, and division using the 8085 microprocessor.

## Apparatus Required:
•	Laptop with internet connection

## Algorithm:

### For Addition (With Carry Consideration):
1.	Load the first number from memory location 4200H into register A.
2.	Load the second number from memory location 4201H into register B.
3.	Add the contents of registers A and B.
4.	If carry is generated, store carry in 4301H.
5.	Store the sum in memory location 4300H.
   
### Program:

```
LDA 4200H
MOV B,A
LDA 4201H
ADD B
STA 4300H
JC STORE_CARRY
HLT
STORE_CARRY:MVI A,01H
STA 4301H
HLT
```

### Output:

<img width="1802" height="714" alt="Screenshot 2026-02-02 111135" src="https://github.com/user-attachments/assets/574cc886-3cac-4ae3-bc24-993ddb324c49" />

<img width="1809" height="662" alt="Screenshot 2026-02-02 111217" src="https://github.com/user-attachments/assets/86a1afff-2ddc-44c6-88f4-d135441b8c64" />

<img width="759" height="1280" alt="image" src="https://github.com/user-attachments/assets/9d0fd7b4-2b8b-4bcd-90d2-1f08c22eadb9" />

<img width="1280" height="400" alt="image" src="https://github.com/user-attachments/assets/839058c3-d900-44b0-acb8-940d4ebaa5d9" />

<img width="1074" height="555" alt="image" src="https://github.com/user-attachments/assets/0e421c65-f745-49a9-80f5-d5ad775abfc6" />


### For Subtraction (Considering Greater Number):
1.	Load the first number from memory location 4200H into register A.
2.	Load the second number from memory location 4201H into register B.
3.	Compare A and B.
4.	If A < B, swap the values of A and B to ensure positive result.
5.	Subtract the content of B from A.
6.	Store the result in memory location 4300H.

### Program:

```
LDA 4200H
MOV C,A
LDA 4201H
CMP C
JC SWAP
MOV B,A
MOV A,C
SWAP: SUB B
STA 4300H
HLT
```

### Output:

<img width="1814" height="607" alt="Screenshot 2026-02-02 111357" src="https://github.com/user-attachments/assets/bbf3f9f3-871f-4a45-8284-8174d23a4a33" />

<img width="1807" height="610" alt="Screenshot 2026-02-02 111422" src="https://github.com/user-attachments/assets/1bd06ad3-cf91-4850-be75-d49bb4edb704" />

<img width="1276" height="1280" alt="image" src="https://github.com/user-attachments/assets/62076529-42ee-40c9-b0c9-3be8237b8fbb" />

<img width="945" height="1600" alt="image" src="https://github.com/user-attachments/assets/dca0f3b4-a25d-4093-8bfa-7a607d27b2c6" />

<img width="1600" height="767" alt="image" src="https://github.com/user-attachments/assets/15ceff03-96eb-44bc-9c3f-4d88802c5b3e" />


### For Multiplication:
1.	Load the first number from memory location 4200H into register A.
2.	Load the second number from memory location 4201H into register B.
3.	Multiply A and B using repeated addition.
4.	Store the result in memory locations 4300H and 4301H (if required for higher bits).

### Program:

```
LDA 4200H
MOV C, A
LDA 4201H
MOV B,A
MVI A, 00H
LOOP: ADD C
DCR B
JNZ LOOP
STA 4300H
HLT
```

### Output:

<img width="1813" height="613" alt="Screenshot 2026-02-02 111532" src="https://github.com/user-attachments/assets/21f089a7-1e63-47e6-a99a-1bc7279b7624" />

<img width="1803" height="599" alt="Screenshot 2026-02-02 111551" src="https://github.com/user-attachments/assets/9f21a474-7d58-4fc7-929c-8365c3bd6a68" />

<img width="1005" height="1600" alt="image" src="https://github.com/user-attachments/assets/57295544-b483-478f-be80-540df44352b5" />

<img width="899" height="1600" alt="image" src="https://github.com/user-attachments/assets/fd5454c1-2557-44ef-97d3-3e311e28623a" />

### For Division:
1.	Load the dividend from memory location 4200H into register A.
2.	Load the divisor from memory location 4201H into register B.
3.	Perform division using repeated subtraction.
4.	Store the quotient in 4300H and remainder in 4301H.

### Program:

```
LDA 4200H
MOV C,A
LDA 4201H
MOV B, A
MVI A, 00H
LOOP: MOV A,C
CMP B
JC END
SUB B
MOV C, A
INR D
JMP LOOP
END: MOV A, D
STA 4300H
MOV A, C
STA 4301H
HLT
```

### Output:

<img width="1829" height="838" alt="Screenshot 2026-02-02 111823" src="https://github.com/user-attachments/assets/df89cff9-e3ea-4173-8452-5d8cbd0542f8" />

<img width="1817" height="843" alt="Screenshot 2026-02-02 112132" src="https://github.com/user-attachments/assets/49d0e607-14a3-4cfd-b79b-4147ba99c6c5" />

<img width="873" height="1403" alt="image" src="https://github.com/user-attachments/assets/84b98552-cd86-4371-b575-df6ab7204a24" />

<img width="1020" height="1599" alt="image" src="https://github.com/user-attachments/assets/bbccd410-9ff3-4472-ab2f-937be4be8e71" />

<img width="1600" height="656" alt="image" src="https://github.com/user-attachments/assets/0d61a2c4-77e5-4a40-918f-be9f4254963d" />


## Result:
The 8-bit arithmetic operations using the 8085 microprocessor have been successfully executed and verified using memory access for input and output.

