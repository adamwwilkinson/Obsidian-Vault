Created: 30/08/2022 at 10:11
Tags: #topic/programming 
Related:[[Pointers]]

### Problems to Solve
We do not know until the function is called, how big an array should be.
Often we do not know how much memory we need until we execute out programs.

To fix these problems we can *dynamically request* new memory at runtime.

### `malloc()`
Declared in `<stdlib.h>` and returns a [[Pointers#What are Pointers|generic pointer]].
`malloc()` needs to be informed of the number of bytes we require.

The datatype it uses is called `size_{t}` to hold an integer value to be 0 or positive.
This is also the returned datatype of the `sizeof` operator, and the type returned of the `strlen()` function.

If we fail to get the memory requested, we **MUST** exit and call a crash.
```ad-warning
The consequence of this is that everytime we call `malloc()`, we must always have a check to see if the variable requesting it isn't null. This should also happen when we call `calloc()`.
```

```c
#include <stdlib.h>

  size_t bytes_wanted   = 1000000 * sizeof(int);

  int    *huge_array    = malloc( bytes_wanted );

  if(huge_array == NULL) {   // DID malloc FAIL?
      printf("Cannot allocate %i bytes of memory\n", bytes_wanted);    
      exit( EXIT_FAILURE );
  }
```

### Cleaning Up the Mess
#### `calloc()`
`calloc()` is used to to clear the memory at a place to all equal 0.

```c
include <stdlib.h>

extern void *calloc( size_t nitems, size_t itemsize );
    ....
    int  *intarray = calloc(N, sizeof(int));
```

#### `free`
For programs that takes a long time, or that needs loads of memory for a time and then no longer require it.
Pass in a pointer of any datatype to give that piece of memory back to the [[Operating Systems|OS]] to reuse. 

```c 
extern void free( void *pointer );
```

```c
#include <stdlib.h>

    int   *vector = randomints( 1000 );

    if(vector != NULL) {
        // USE THE vector
        ......
        free( vector );
    }
```

The length of a pointer is kept in the spot in memory one slot before the pointer.
This is why we do not need to pass the length of the pointer to `free()`.

```ad-info
We can only free memory created by `malloc()` or `calloc()`.
```

### Reallocating Previous Memory
When we use `malloc()` again after freeing, it will try used the free block.

We can use `realloc()` to grow or shrink previously allocated memory.

```c 
extern void *realloc( void *oldpointer, size_t newsize );
```

```ad-info
`realloc()` either grows at the place of the original pointer, or if there is not enough contigous memory, it will copy the pointer
and paste it in a new place, returning the pointer of that new location.
```
