Created: 2022-10-23 21:03
Tags: #topic/programming 
Related:

### What
A program is considered *portable* if it can  be 'moved' or migrated to different computing environments

As C is hardware dependent, it is important that:
- hardware-dependent code has been identified and isolated
- software abstraction and application-programming interfaces hide characteristics from applications
- successful applications do not introduce, or depend upon, hardware dependencies

### Version Checking and OS Checking
We can have to compiler identify the version it is on, and do certain actions depending.
```c
#include <stdio.h>

int main(int argc, char *argv[])
{
#if __STDC_VERSION__ >=  201710L
    printf("hello from C18!\n");

#elif __STDC_VERSION__ >= 201112L
    printf("hello from C11!\n");

#else
    #error This program demands features from C11 or later

/*
#elif __STDC_VERSION__ >= 199901L
    printf("hello from C99!\n");
#else
    printf("hello from (ANSI-C) C89/C90!\n");
 */

#endif

    return 0;
}
```

We can also check the OS we are on.
```c
#ifdef _WIN64
   //define something for Windows (64-bit)
#elif _WIN32
   //define something for Windows (32-bit)
#elif __APPLE__
    #include "TargetConditionals.h"
    #if TARGET_OS_IPHONE && TARGET_IPHONE_SIMULATOR
        // define something for simulator   
    #elif TARGET_OS_IPHONE
        // define something for iphone  
    #else
        #define TARGET_OS_OSX 1
        // define something for OSX
    #endif
#elif __linux
    // linux
#elif __unix // all Unix-derived systems not detected above
    // Unix
#elif __posix
    // POSIX
#else
    #error unrecognized operating system platform
#endif
```

### Employing the Correct Sized Integers for Portability
Previously we have not cared whether the host architecture supported integers of length 16, 32, or 64 bits. For different application the storage size of an integer may be significant, and a portable program should enforce its requirements.

Using the header file `<inttypes.h>` we can define how to perform IO on integers.
```c
#include <stdint.h>
#include <inttypes.h>

    int64_t    nbytes;
    ....
    printf("%" PRIi64 "MB\n", n / (1 << 20) );
```

### Unicode Support in C11
Portable programs should not be limited to communicating only in English and English alphabet characters.
As some characters of different languages may need more than one byte to be stored in, we need this information to be encoded.
