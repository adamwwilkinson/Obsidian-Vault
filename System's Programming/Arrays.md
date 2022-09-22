Created: 09/08/2022 at 09:59
Tags: #topic/programming 
Related: [[The Programming Language C]]

### Context
Back in the old days, hardware was very slow. C was developed in these dark ages and thus was meant to be very fast.

### Dimension
C supports arrays of any dimension. 1-dimensional arrays are called *vectors*, 2-dimensional arrays are called *matrices*, and 3-dimensional arrays are *volumes*.

#### 2-D Arrays in Memory
Memory is only grabbed in 1 dimension, this means a 2-dimensional array is instead seen as a long vector. This makes more sense to take a slice of a 2-dimensional array, as it takes it from a start point in that 1-dimensional line in an array. 

Columns are slow to get instead of rows because adjacent elements in column space are far apart in memory.

### Why Start at 0
Instead of an 'index' C instead thinks of it as an offset. Where the first element has an offset of 0. The offset has a certain amount of bytes to it, and an offset of 1 for a 4 byte integer would be 4 bytes 'along'.

#### Negative Values
Can be used to retrieve seemingly arbitrary values. Can be dangerous if you don't know what you are doing.

### Initialisation
C does not initialise values to be 0 as default. This means we have to initialise them ourselves,
```c
#define N 5

int myarray[N];
for (int i = 0; i < 6; i++){ //initialise at compile time
myarray[i] = i;
}

int myarray[N] = {0, 1, 2, 3, 4, 5}; //intialise at runtime

# define N (sizeof(myarray) / sizeof(myarray[0])) //let compile time do the work
```
[[The Programming Language C#Compile Time vs Runtime|Compile and Runtime]] 

Global values are guaranteed to be initialised to 0 as default because this can be done extremely fast.

### Variable Length Arrays
Pass an array by giving its name, as well as passing its size when passing an array as a function. 
Reason that it's necessary:
- We dynamically allocate memory a lot.
- We can't look at an array and work out how big it is.

### Strings
Strings are just vectors of *characters*. It allocates the `word.length + 1` bytes of memory in order to have a *null byte*. This *null byte* isn't counted when asked for the length of the string, but would still need to be explicitly stated when copying it over.

This *null byte* looks like `\0`. 

#### Functions
```c
#include  <string.h>

// which declares many functions, including:_

int strlen( char string[] ); // to determine the length of a string

int strcmp( char str1[],  char str2[] ); // to determine if two strings are equal

char *strcpy( char destination[],  char source[] ); // to make a copy of a string
```
