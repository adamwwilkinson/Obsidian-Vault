# OS Services
Created: 23/08/2022 at 13:52
Tags: #topic/software 
Related: [[Operating Systems]]

All OSs provide service points through which an application may request services of the OS kernal. The points are called *system calls*.

### Interfaces to C
The system call interfaces of modern operating systems are presented as an API of C-language prototypes, regardless of the choice of the application language.

```c
#include <syscall.h>
#include <unistd.h>
.....

int write(int fd, void *buf, size_t len)
{
    if (any_errors_in_arguments) {
       errno = EINVAL;
       return (-1);
    }
    return syscall(SYS_write, fd, buf, len);    
}
```

Don't do the syscall unless sure no errors pop up as syscalls are expensive.

### Status Values Returned from System Calls
```c
#define EPERM     1     /* Operation not permitted */
#define ENOENT    2     /* No such file or directory */
#define ESRCH     3     /* No such process */
#define EINTR     4     /* Interrupted system call */
#define EIO       5     /* I/O error */
#define ENXIO     6     /* No such device or address */
#define E2BIG     7     /* Arg list too long */
#define ENOEXEC   8     /* Exec format error */
#define EBADF     9     /* Bad file number */
#define ECHILD   10     /* No child processes */
```

### Using `errno` and `perror()`
There is an array of strings called `sys_errlist[]` that can be used for better diagnostics.
```c
#include <stdio.h>
#include <stdlib.h>
#include <errno.h>
    ...

    if(chdir("/Users/someone") != 0) {
       printf("cannot change directory, why: %s\n", sys_errlist[errno]);
       exit(EXIT_FAILURE);
    }
    ...
```
or alternatively we can just pass the arguement to `perror()` which does it for us.
```c
#include <stdio.h>
#include <stdlib.h>
#include <errno.h>
    ...

int main(int argc, char *argv[])
{
    ...
    if (chdir("/Users/someone") != 0) {                                 
       perror(argv[0]);
       exit(EXIT_FAILURE);
    }
    ...
```
