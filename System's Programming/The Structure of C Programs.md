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