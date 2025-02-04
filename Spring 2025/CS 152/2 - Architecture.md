---
tags:
  - cs152
---
## Symbolic Logic
* Deals with the representation and technique of algebra that separates the meaning of factual statements and from proofs of their consistency and their truth values
### [Binary](../CS%2047/2%20-%20Number%20Systems.md#Base%202) Operators
#### Common Operators
##### OR
- $Y=A+B$

| $A$ | $B$ | $Y$ |
| --- | --- | --- |
| $0$ | $0$ | $0$ |
| $0$ | $0$ | $0$ |
| $1$ | $0$ | $1$ |
| $1$ | $1$ | $1$ |
##### NOT
- $Y=\overline{A}$

| $A$ | $Y$ |
| --- | --- |
| $0$ | $1$ |
| $1$ | $0$ |
##### BUF
- $Y=A$ 

| $A$ | $Y$ |
| --- | --- |
| $0$ | $0$ |
| $1$ | $1$ |
##### AND
- $Y=AB$

| $A$ | $B$ | $Y$ |
| --- | --- | --- |
| $0$ | $0$ | $0$ |
| $0$ | $0$ | $0$ |
| $1$ | $0$ | $0$ |
| $1$ | $1$ | $1$ |
##### XOR
- $Y=A\oplus B$

| $A$ | $B$ | $Y$ |
| --- | --- | --- |
| $0$ | $0$ | $0$ |
| $0$ | $0$ | $1$ |
| $1$ | $0$ | $1$ |
| $1$ | $1$ | $0$ |
##### NAND
- $Y=\overline{AB}$

| $A$ | $B$ | $Y$ |
| --- | --- | --- |
| $0$ | $0$ | $1$ |
| $0$ | $0$ | $1$ |
| $1$ | $0$ | $1$ |
| $1$ | $1$ | $0$ |
##### NOR
- $Y=\overline{A+B}$

| $A$ | $B$ | $Y$ |
| --- | --- | --- |
| $0$ | $0$ | $1$ |
| $0$ | $0$ | $0$ |
| $1$ | $0$ | $0$ |
| $1$ | $1$ | $0$ |
##### XNOR
- $Y=\overline{A\oplus B}$

| $A$ | $B$ | $Y$ |
| --- | --- | --- |
| $0$ | $0$ |     |
| $0$ | $0$ |     |
| $1$ | $0$ |     |
| $1$ | $1$ |     |
#### Precedence
* Parenthesis
* NOT
* AND (AND, NAND)
* OR (OR, NOR, XOR)
#### Truth Tables
- Consider a Boolean function $N$ containing $n$ Boolean variables $a_0,a_1,...,a_{n-1}$
- A truth table may be constructed containing $2^n$ rows which gives the value of $N$ for every combination of truth values of the variables $a_0,a_1,...,a_{n-1}$
#### Evaluating Logical Expressions
##### ~
- Negation
- Ex. ~$(AB)$ is the negation of $A$ and$B$
##### $\rightarrow$
- Implication
- Ex. $A\rightarrow B$
	- True except when $A$ is true but $B$ is false
#### Tautology
- A logical expression that is true for every combination of truth values of its variables
## Computer Architecture
### MIPS Assembly Language
#### Register Set

| Name           | Number  | Use                     |
| -------------- | ------- | ----------------------- |
| $\$0$          | 0       | the constant value 0    |
| $\$at$         | 1       | assembler temporary     |
| $\$v0-\$v1$    | 2 - 3   | procedure return values |
| $\$a0-\$a_{3}$ | 4 - 7   | procedure arguments     |
| $\$t0-\$t7$    | 8 - 15  | temporary variables     |
| $\$s0-\$s7$    | 16 - 23 | saved variables         |
| $\$t8-\$t9$    | 24 - 25 | temporary variables     |
| $\$k0-\$k1$    | 26-27   | OS temporaries          |
| $\$gp$         | 28      | global pointer          |
| $\$sp$         | 29      | stack point             |
| $\$fp$         | 30      | frame pointer           |
| $\$ra$         | 31      | procedure return addres |

| High Level Code | MIPS Assembly Code             |
| --------------- | ------------------------------ |
| $a=b+c$         | `add a, b, c`                  |
| $a=b-c$         | `sub a, b, c`                  |
| $a=b+c-d$       | `sub t, c, d`<br>`add a, b, t` |
|                 |                                |
#### Memory
- Commonly used variables are kept in registers
- By using a combo of memory and registers a program can access a large amount of data fairly quickly
- Drawn with low memory addresses toward bottom and high memory addresses toward top
- Byte-addressable memory (each byte has a unique address)
- MIPS uses 32 bit memory addresses and 32 bit data words