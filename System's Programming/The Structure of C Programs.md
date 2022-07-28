# The Structure of C Programs
Created: 28/07/2022 at 20:17
Tags: #topic/programming 
Related:

### Whitespaces
Only used for human readability, not required for the compiler.

### Preprocessor
Lines usually starts with a # and are at the beginning, with the output of the 
preprocessor being sent to the processor.
The lines here affect the later body of code.

#### Stdio.h
 Stands for standardio, the .h in the file refers to it being a header file. .c is for c source files.

#### # Defines
```c
#define ROT 13
```
Defines a constant using the C preprocessor.

### Compiling
Takes a file ending in .c and compiles it to be executable. C programs are *human-readable* also known as *source-code files*. The compiler turns it to an [[Object File]] which is not *human-readable* which is then given to a linker, which now takes the object files from the library files and links them, and makes all that into an executable file.

### Variable
Are case-sensitive, usually aren't fully uppercase except in the case constants for the C preprocessor.

#### Basic Datatypes
- bool
- char
- int
- float
- double

#### Integers
sizeof(char) $\leq$ sizeof(short) $\leq$ sizeof(int) $\leq$ sizeof(long)

All these sizes are different on different architectures but each level is double the level before.

### Control of Flow
#### If
```c
if(condition){
//block
}
elseif (condition2){
// block
}
else {
// block
}
```

#### Switch
```c
if (expression == value1) {
// block
}
else if (expression == value2) {
// block
}
else {
// block
}

// Switch equivalent:

switch (expression) {
	case value1:
		// block
		break; // takes control flow to the bottom
	case value2:
		// block
		break;
	default :
		// block
		break;
}
```

#### While loop vs do while loop
While loops can be terminated immediately, which do while loops run at least once.
```c
do {
	// block
}
while (

	// condition
)
```

#### Break and Continue
Break breaks a loop to the bottom, continue restarts to the top of the loop.

#### For loops
```c
for ( expr1; expr2; expr3){
	statement1;
}

// the equivalent to

expr1;
while(expr2){
	statement1;
	...
	expr3
}
```

### Boolean
Integers of value 0 are seen as *false*, while all others are seen as *true*. If we want to use *true* and *false* constants we need to provide the line. `#include <stdbool.h>` like [[#Stdio h]].