```mermaid 
graph
1[Source File] --> 2[Assembler] --> 3[Object File]
4[Source File] --> 5[Assembler] --> 6[Object File]
7[Source File] --> 8[Assembler] --> 9[Object File]
3 --> 11[Linker]
6 --> 11
9 --> 11
11 --> 12[Loader]
```
## Assembler
### Label
- Used for things like [jump instructions](3%20-%20Programming%20a%20Computer.md#^72cc66) and loops
#### Relative Addressing
- The instruction (usually line) number
### Lexemes
- Breaking down each line of the MIPS code