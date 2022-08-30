# Pointers
Created: 29/08/2022 at 21:40
Tags: #topic/programming 
Related: [[The Programming Language C]]

### Primary Role
Allow a program to access its own memory. This means you can treat any part of memory anyway you want.

### What are Pointers?
1. *Variables* that *hold* the address of a memory location.
2. *Variables* that *point* to memory locations.
3. Usually something that *point* to memory locations being used to hold variables' values.

### The &
The *address-of* operator that is used to find a variable's address.
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

#### The `void *`
Highlights that variable is a generic pointer.

### Dereferencing the Pointer
In the above example, if we used `*p*` it will return the value held at that spot in memory.

### [[Arrays]]? 
```c 
int *p = &totals[0];
int *p = totals;
```
The array's name is synonymous with the address of the first element.

### Incrementing Pointers
When incrementing the pointer, it increases itself by the size of the variable.
This means for an array holding 4 byte integers, when the pointer to the first is `p++` adds to itself 4 to point to the next integer in the array.

### Passing Pointers to Functions
Passing the name of the variable to a function isn't enough as that gives a copy of the value, rather then the adress in memory.
Instead we pass the pointers of those variables to directly modify them.

We can't give away to someone the address of our local variable, once the function containing that variable ceases.

Now we look at [[Dynamic Memory]].
