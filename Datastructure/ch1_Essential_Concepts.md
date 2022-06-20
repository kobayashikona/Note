# Essential Concepts

Programming and problem solving are different. Programming is something like syntax and language which can be learned in several days. While problem solving is a lifetime. You should be good at mathematics since if you are solving a problem, solution will be given in mathematics.

## Array
```c++
int A[5]; \\declare
int B[5]={2,5,8,1,6}; \\declare and initialize
```
Main memory are divided into code section, stack and heap. The varibles defined in the body of the function are stored inside the stack,such as the arrays above.

### Variable Sized Array
It's allowed to creat an array whose size is identified by a variable instead of a const. In this way, we can't initialize this array when creating it.
```c++
int n;
std::cin >> n;
int A[n]; //It's not allowed to create array like int A[n]={2,4,6,8};
```

## Structure

```c++
//declaration of a structure type should be put in front of the main function
struct rectangle
{
    double length;
    double breadth;
}; //don't ignore the semicolon behind curly brace

int main()
{
    struct rectangle r1;//don't ignore "struct" when defining a variable of type structure
    struct rectangle r2={10,5};//declare and initialize
    r1.length=15; //We can use dot operator so as to access a member.
}
```
The variable is created inside the stack for the main function.

When there are multiple elements in the structure, the minimum unit of memory allocation is 4 bytes,for example:
```c++
struct Rectangle
{
    int length;
    int breadth;
    char c;
}r;
```
If we check the size of r, we will find it access 12 bytes space and use 9 of them.

## Pointers

Pointers are address variable which are used for indirectly accessing the data.

1. Program can access stack and code section, while it can't access heap. So one reason for using pointers is to access memory in heap.
2. One major using of pointers is accessing the resources which are outside the program, such as disk, monitors, keyboardand internet.
3. Parameter passing.

```c++
int a=10; //data variable
int *p; //address variable
p=&a; //initialize p with address of a
printf("%d",p); //address stored in p;
printf("%d",*p); //dereferencing, value stored in the address p points
```

```c++
p=(int *)malloc(n*sizeof(int));
```