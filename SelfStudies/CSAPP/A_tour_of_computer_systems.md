

# 1.2 Different forms of a program

**Machine-language**: C statements must be translated into of sequence of such instructions

**Executable object program**: packaged into such form, then stored as binary disk file

![[Pasted image 20240825175809.png]]

`linux> gcc -o hello hello.c`

**Compilation phase: 
- <u>Preprocessing</u> modifies the C program according to directives that begin with the '#' char. Result is another C program, typically with `.i` suffix
- <u>Compilation</u> translates `hello.i` -> `hello.s` , containing an *assembly language* program. Eg: ![[Pasted image 20240825230943.png]]
- <u>Assembly</u> , assembler translates `hello.s` into machine-language instructions, packages them in a form: *relocatable object program*, stores output in `hello.o` (binary file)
- 