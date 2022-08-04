# Functions in C
Created: 04/08/2022 at 16:41
Tags: #topic/programming 
Related: [[The Structure of C Programs]], [[The Programming Language C]]

### C is a Procedural Language
C's primary synchronous control flow mechanisms is the *procedure call*.

### Why do we Need Functions?
1. Allow us to group together statement that are strongly related
2. Follow DRY principals
3. Well-defined entry points
4. Convenient way to package and distribute code
5. Processes can share a single instance of a function

### The Role of `main()`
`main()` should be constrained to:
- receive command-line arguments
- report errors win those arguments and call `exit(EXIT_FAILURE)`
- call functions
- call `exit(EXIT_SUCCESS)`
- error messages to be printed to the *stderr* #todo/linkit stream
- 'normal' output to be printed to the *stdout* stream

### Datatypes of Functions
- functions that don't return anything `void`
- functions that do return a value, such as `int`, `char`, `bool`, or `float`

### Passing Parameters
*Order of evaluation* is not defined in C. Do not assume it is left to right.

### `static`
If `static` appears before a global variable or function, it defines it to be global in only that file.

If `static` appears before a local variable within a function, it says that variable retains its values between calls. Typically, used to count the amount of times a function has been called.
