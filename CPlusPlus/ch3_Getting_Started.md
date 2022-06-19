# Getting Started

## How to Build Your Program

**Building** means **compiling**, **linking** together with extra libraries and external files if we need to and **creating** an executable file.

## Errors

### Compiler Errors

- syntax errors - something wrong with the structure,e.g.`return 0`
- semantic errors - something wrong with the meaning,e.g.`a+b`

### Compiler Warnings

- The compiler has recognized an issue that could lead to a potential problem.
- It's only a warnging because the compiler can still generate correct machine code.
e.g.
```c++
int mile;
std::cout << mile; //mile is used uninitialized
```

### Linker Errors

Linker error ususlly happens when there is a library or object file that is missing.e.g.
```c++
#include <iostream>
extern int x;
int main()
{
    std::cout << x;//undefined reference x
}
```

### Runtime Errors

Runtime errors occurs when program is executing,for example:
- divided by zero
- file not ffound
- out of memory

### Logic Errors

Logic Errors are mistakes made by programmer. Sometimes mistakes are caused by incomplete or incorrect information.

