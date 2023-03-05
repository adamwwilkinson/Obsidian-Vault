Created: 2022-10-09 11:51
Tags: #topic/programming 
Related: [[The Structure of C Programs]]

### The Standard Command-Line Arguments
`argc` - provides the count of the number of arguments
All recieve programs at least one argument (the programs name)

#### What is `argv`
It is an array of pointers to characters, with the first element in the array pointing to the program's name.

### Parsing Arguments
If we want to toggle an option in a program, and we can look through the passed arguments character by character,
we can say options for the program are precedded by '-' or a '+'.

### Using `getopt()`
As programs get more complicated we can use `getopt()` to support our passing of command-line arguments.

It is not a function in the Standard C library, but it is widely available and used.

```c
#include <stdio.h>
#include <stdbool.h>
#include <unistd.h>

#include <getopt.h>

#define	OPTLIST		"d"

int main(int argc, char *argv[])
{
    int		opt;

    .....
    opterr	= 0;
    while((opt = getopt(argc, argv, OPTLIST)) != -1) {
	if(opt == 'd')
            dflag = !dflag;
        else
            argc = -1;
    }
    if(argc < 0) {
        fprintf(stderr, "Usage: %s [-d] [filename]\n", progname);  
        exit(EXIT_FAILURE);
    }
    while(optind < argc) {
        process( argv[optind] );
        ++optind;
    }
    .....
    return 0;
}
```

#### A More Complicated Example
```c
#include <stdio.h>
#include <stdbool.h>
#include <stdlib.h>
#include <string.h>
#include <unistd.h>

#include <getopt.h>

#define	OPTLIST		"df:n:"

int main(int argc, char *argv[])
{
    int  opt;
    bool dflag   = false;
    char *filenm = NULL;
    int  value   = DEFAULT_VALUE;

    opterr	= 0;
    while((opt = getopt(argc, argv, OPTLIST)) != -1)   {  
//  ACCEPT A BOOLEAN ARGUMENT
	if(opt == 'd') {
            dflag  =  !dflag;
        }
//  ACCEPT A STRING ARGUMENT
	else if(opt == 'f') {
            filenm  =  strdup(optarg);
        }
//  ACCEPT A INTEGER ARGUMENT
	else if(opt == 'n') {
            value  =  atoi(optarg);
        }
//  OOPS - AN UNKNOWN ARGUMENT
        else {
            argc = -1;
        }
    }

    if(argc <= 0) {    //  display program's usage/help   
        usage(1);
    }
    argc  -= optind;
    argv  += optind;
    .....
    return 0;
}
```

### Inter-process Communication
 Processes do not, and should not work in isolation, and should communicate with other processes if useful.

#### Filters
The '|' symbol passes the output of one process to be inputted in the next process. This means you can filter the output of a process by passing it through a pipeline.

#### Pipes in C
We can use `pipe()` to create a unidirectional communication buffer.
Within the OS kernal, a pipe is a vector in memory, typically 4096 bytes long.
Within a C program, a pipe is represented by an array of two integer file-descriptors. Writing to array[0] adds data to the pipe, and reading from array[1] removes that data.

```c
#include  <unistd.h>

int  thepipe[2];
char data[1024];
int  datasize, nbytes;

if(pipe(thepipe) != 0) {
    perror("cannot create pipe");
    exit(EXIT_FAILURE);
}

datasize = ...
nbytes   = write( thepipe[0], data, datasize);       // write to the pipe

nbytes   =  read( thepipe[1], data, sizeof(data));   // read from the pipe
```

Used for scheduling processes:
- A newly created pipe is empty
- Data written is added to the pipe
- If a process tries to write more data than will fit in the pipe, the process is blocked until space becomes available
- Data read is removed from the pipe
- If a process tries to read an empty pipe, or more data than is held in the pipe, it is blocked until data becomes available

```c
#include  <stdio.h>
#include  <stdlib.h>
#include  <unistd.h>

void communicate(void)
{
    int  thepipe[2];
    char data[1024];
    int  datasize, nbytes;

    if(pipe(thepipe) != 0) {
        perror("cannot create pipe");
        exit(EXIT_FAILURE);
    }

// fork()ing THE PROCESS WILL DUPLICATE ITS DATA, INCLUDING THE pipe'S TWO FILE-DESCRIPTORS

    switch ( fork() ) {
    case -1 :
        printf("fork() failed\n"); // process creation failed
        exit(EXIT_FAILURE);
        break;

    case 0:                       // new child process
        close( thepipe[1] );      // child will never write to pipe
        nbytes = read( thepipe[0], data, sizeof(data));   // read from the pipe
        ....
        close( thepipe[0] );

        exit(EXIT_SUCCESS);
        break;

    default:                      // original parent process
        close( thepipe[0] );      // parent will never read from pipe
        datasize = ...
        nbytes   = write( thepipe[1], data, datasize);    // write to the pipe
        ....
        close( thepipe[1] );
        break;
    }
}
```

#### A More Realistic Example
```c
#include  <stdio.h>
#include  <stdlib.h>
#include  <unistd.h>

void communicate(void)
{
    ....
    switch ( fork() ) {
    ....

//  CHILD PROCESS RUNS sort, READING ITS stdin FROM THE PIPE
    case 0  :                     // new child process
        close( thepipe[1] );      // child will never write to pipe
        dup2(  thepipe[0], 0);    // duplicate/clone the reading end's descriptor and stdin 
        close( thepipe[0] );      // close the reading end's descriptor

        // child may now read from its stdin (fd=0)

        execl("/usr/bin/sort", "sort", NULL);   // execute a new (filter) program
        perror("/usr/bin/sort");

        exit(EXIT_FAILURE);
        break;

    default :                     // parent process
        close( thepipe[0] );      // parent will never read from pipe
        dup2(  thepipe[1], 1);    // duplicate/clone the writing end's descriptor and stdout 
        close( thepipe[1] );      // close the writing end's descriptor

        // parent may now write to its stdout (fd=1)
        ....
        break;
    }
}
```
