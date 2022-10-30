Created: 2022-10-03 15:20
Tags: #topic/programming 
Related:[[the programming language c]], [[the structure of c programs]]

### What is cc
*cc* is a front-end program to a number of *passes* of the activity of "converting" our C source files to executable programs:

1. For every C source file we parse, generate, and optimise that code, outputted to an object file
2. All necessary object files are presented to a program called the *linker*
3. The linker's output is written to the disk as an executable file

### Developing Larger C Programs into Multiple Files
Like we divide a single main function to multiple smaller ones, we can divide a program into multiple files.

There are some benifits to this, like:
- each file is focused for a single role
- global variable are reduced
- large projects may be undertaken by multiple people

#### How?
A header file can be created, which declares all the functions to use.
```c
#include  <stdio.h>
#include  <stdbool.h>
#include  <stdlib.h>

// DECLARE GLOBAL PREPROCESSOR CONSTANTS
#define  MAXMARKS  200

// DECLARE GLOBAL FUNCTIONS
extern int         readmarks(FILE *); // parameter is not named
extern void        correlation(int);  // parameter is not named

// DECLARE GLOBAL VARIABLES
extern	double     projmarks[];       // array size is not provided
extern	double     exammarks[];
extern	bool       verbose;
```

We then can call it like any other header file but with double quotes instead.
```c
#include "thing.h"
```

```ad-info
The double quotes here tells the C PREPROCESSOR to look locally, while the '<'  tell it to look in the systems folder.
```

### Compiling?
We can have a 50 word command line to compile everything. This is expensive and can be time-consuming to write out every time.

### The Better Way
We can use **make** to only compile files if they don't exist yet or changed. The instructions for this are given in a *Makefile*.

```
# A Makefile to build our 'calcmarks' project

calcmarks : calcmarks.o globals.o readmarks.o correlation.o
—— tab —→cc -std=c11 -Wall -Werror -o calcmarks calcmarks.o globals.o \
		      readmarks.o correlation.o -lm


calcmarks.o : calcmarks.c calcmarks.h
—— tab —→cc -std=c11 -Wall -Werror -c calcmarks.c

globals.o : globals.c calcmarks.h
—— tab —→cc -std=c11 -Wall -Werror -c globals.c

readmarks.o : readmarks.c calcmarks.h
—— tab —→cc -std=c11 -Wall -Werror -c readmarks.c

correlation.o : correlation.c calcmarks.h
—— tab —→cc -std=c11 -Wall -Werror -c correlation.c  
```

Targets are the beginning of the lines, with the things after the colon are the dependencies.
The actions are declared after a tab character.

#### Variable Substutions with **make**
```
# A Makefile to build our 'calcmarks' project

C11     =  cc -std=c11
CFLAGS  =  -Wall -Werror


calcmarks : calcmarks.o globals.o readmarks.o correlation.o
       $(C11) $(CFLAGS) -o calcmarks \
                  calcmarks.o globals.o readmarks.o correlation.o -lm


calcmarks.o : calcmarks.c calcmarks.h
       $(C11) $(CFLAGS) -c calcmarks.c

globals.o : globals.c calcmarks.h
       $(C11) $(CFLAGS) -c globals.c

readmarks.o : readmarks.c calcmarks.h
       $(C11) $(CFLAGS) -c readmarks.c

correlation.o : correlation.c calcmarks.h
       $(C11) $(CFLAGS) -c correlation.c
```
