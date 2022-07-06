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

It's not necessary to use the word struct when we want to declare an object of structure in C++.
```c++
rectangle r = {10, 5}; // It's same as struct rectangle r = {10, 5}; in C++
struct rectangle r = {10, 5}; // We must bring the word struct in C language 
```

## Pointers

Pointers are address variable which are used for indirectly accessing the data.

1. Program can access stack and code section, while it can't access heap. So one reason for using pointers is to access memory in heap.
2. One major using of pointers is accessing the resources which are outside the program, such as disk, monitors, keyboardand internet.
3. Parameter passing.

```c++
int a = 10; //data variable
int *p; //address variable
p = &a; //initialize p with address of a
printf("%d",p); //address stored in p;
printf("%d",*p); //dereferencing, value stored in the address p points
(*p)++; //the value in address p has plus one, so a=11 and p doesn't change.
```

### An Example of Change Value by Pointer

```c++
void func(int *x, int *y)
{
    int t;
    t = *x;
    *x = *y;
    *y = t;
}
int main()
{
    int x = 11, y = 22;
    func(&x,&y);
    std::cout << x << y; //execution is 2211
    return 0;
}
```

**Caution**:Morphological parameters of function are new local variables which is different from the arguments outside the function, even though they have same name.

```c++
void func(int x, int y)
{
    std::cout << &x << std::endl; //address of x here is different from that of x in main()
    int t;
    t = x;
    x = y;
    y = t;
}
int main()
{
    int x = 11, y = 22;
    func(x,y);
    std::cout << &x << std::endl; // address of x here is different from that of x in func()
    std::cout << x << y;//execution is 1122 which means the values of x,y aren't changed
    return 0;
}
```

### Access Memory in Heap

In C language, the function `malloc()` is used to allocate the memory in heap.
In C++ language, the operator `new` is used for the ssame purpose.

```c++
// Pointer p has not been deleted when we release the space it points to, the address it points to hasn't been changed.
// We need to give it a value, otherwise, it will be regarded as a legal pointer while it doesn't points legal memory.
int *p;

p = (int *)malloc(n*sizeof(int));
free (p);
p = NULL; 

// new/delete and new[]/delete[] should be use in pairs.
p = new int[5];
delete []p;
p = NULL;
```

### Pointer to Structure

```c++
struct rectangle r = {10, 5};
struct rectangle *p = &r; //a pointer points to r

// Two ways to ccess member of structure using pointer
(*p).length = 20; // the precedence of . is higher than *
p->length = 20; // we use arrow to access menber of struct p points to
```

**Dynamic structure:**

```c++
// Create a struct in heap
struct rectangle *p;
p = (struct rectangle *)malloc(sizeof(struct rectangle));
p->length = 10;
p->breadth = 5;
```

## Reference

It is another name of a variable. The common use of reference is parameter passing in functions.

```c++
int a = 10;
int &r = a; //r is another name of a. They have same address.

r++; 
std::cout << a; //The value is 11 rather than 10
std::cout << r; //11 as well 
```

**Note:**

- The variable declared by `int *r` will sotre address.
- The variable declared by `int &r` will sotre integer value, and it must be initialized at the same time.
- `int &r = a; r = b;` won't switch r to reference of b, it'll just change the value of a.


## Functions

Function is a piece of code which performs a task.

When a fuction start, local variables in it will be created in stack. And these variables will be deleted once the function ends. 

Ways to pass parameters
1. Pass by Value
```c++
// All changes are done to formal parameters
void swap(int x, int y)
{
    ...
}
...
int a = 10, b = 5;
swap(a, b);
```

2. Pass by Address
```c++
// The changes are done to value stored in corresponding address
void swap(int* x, int* y)
{
    ...
}
...
int a = 10, b = 5;
swap(&a, &b);
```
3. Pass by Reference




## Template