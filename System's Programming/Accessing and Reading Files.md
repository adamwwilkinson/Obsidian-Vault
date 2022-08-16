# Accessing and Reading Files
Created: 16/08/2022 at 10:16
Tags: #topic/programming 
Related: [[The Programming Language C]]

### File Descriptors
A small integer, with min 0 and max (depending on system) 255. if the file is opened succesfully, the OS would return the lowest file descriptor available.

```c
#include  <stdio.h>
#include  <fcntl.h>
#include  <stdlib.h>
#include  <unistd.h>
#define  MYSIZE      10000

void read_using_descriptor(char filename[])        
{
//  ATTEMPT TO OPEN THE FILE FOR READ-ONLY ACCESS
    int fd    = open(filename, O_RDONLY);

//  CHECK TO SEE IF FILE COULD BE OPENED
    if(fd == -1) {
        printf("cannot open '%s'\n", filename);
        exit(EXIT_FAILURE);
    }

//  DEFINE A CHARACTER ARRAY TO HOLD THE FILE'S CONTENTS
    char   buffer[MYSIZE];
    size_t got;

//  PERFORM MULTIPLE READs OF FILE UNTIL END-OF-FILE REACHED  
    while((got = read(fd, buffer, sizeof buffer)) > 0) {  
        .....
    }

//  INDICATE THAT THE PROCESS WILL NO LONGER ACCESS FILE
    close(fd);
}
```

Functions *open, read* and *close*, are not C11 functions but rather OS **system-calls**.


