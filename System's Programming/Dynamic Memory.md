# Dynamic Memory
Created: 30/08/2022 at 10:11
Tags: #topic/programming 
Related:[[Pointers]]

### Problems to Solve
We do not know until the function is called, how big an array should be.
Often we do not know how much memory we need until we execute out programs.

To fix these problems we can *dynamically request* new memory at runtime.

### `malloc()`
Declared in `<stdlib.h>` and returns a [[genric pointer]] #todo.
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
