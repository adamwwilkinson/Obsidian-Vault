# Pointers
Created: 29/08/2022 at 21:40
Tags: #topic/programming 
Related: [[The Programming Language C]]

### Primary Role
Allow a program to access its own memory. This means you can treat any part of memory anyway you want.

### What are Pointers?
1. *Variables* that *hold* the adress of a memory location.
2. *Variables* that *point* to memory locations.
3. Usually something that *point* to memory locations being used to hold variables' values.

### The &
The *adress-of* operator that is used to find a variable's address.
```c 
int total;
... &total ...
```

### The *
Denotes a pointer.
```c 
int total;
int *p;
p = &total;
```
