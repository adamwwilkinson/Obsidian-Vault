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

### Reading Human Readable Text Files
We open the file using C's `fopen()`. The returned value is a *FILE pointer*, that is later used in all subseqquent operations.

```c

#include <stdio.h>

#define DICTIONARY      "/usr/share/dict/words"

....
//  ATTEMPT TO OPEN THE FILE FOR READ-ACCESS
    FILE   *dict = fopen(DICTIONARY, "r");

//  CHECK IF ANYTHING WENT WRONG
    if(dict == NULL) {
        printf( "cannot open dictionary '%s'\n", DICTIONARY);
        exit(EXIT_FAILURE);
    }

//  READ AND PROCESS THE CONTENTS OF THE FILE
    ....

//  WHEN WE'RE FINISHED, CLOSE THE FILE
    fclose(dict);
```

#### Declaring Usage
"r" 	open for reading
"r+" 	open for reading and writing
"w" 	create or truncate file, then open for writing
"w+" 	create or truncate file, then open for reading and writing
"a" 	create if necessary, then open for appending (at the end of the file)
"a+" 	create if necessary, then open for reading and appending

#### Reading Individual Lines
```c
#include <stdio.h>

....
    FILE   *dict;
    char   line[BUFSIZ];

    dict = fopen( ..... );
    ....

//  READ EACH LINE FROM THE FILE,
//  CHECKING FOR END-OF-FILE OR AN ERROR
    while( fgets(line, sizeof line, dict) != NULL ) {  
        ....
        ....     // process this line
        ....
    }
//  AT END-OF-FILE (OR AN ERROR), CLOSE THE FILE
    fclose(dict);
```

#### Trimming End-of-line Characters
```c
//  REMOVE ANY TRAILING end-of-line CHARACTERS FROM THE LINE
void trim_line(char line[])
{
    int i = 0;

//  LOOP UNTIL WE REACH THE END OF line
    while(line[i] != '\0') {

//  CHECK FOR CARRIAGE-RETURN OR NEWLINE
        if( line[i] == '\r' || line[i] == '\n' ) {
            line[i] = '\0'; // overwrite with null-byte
            break;          // leave the loop early
        }
        i = i+1;            // iterate through character array
    }
}
```

#### Writing 
Instead of `fgets()` for retrieving a line of text `fputs()` outputs a line of text.

### Reading Binary Files using the Standard Library
`fgets()` manages differing lines by reading until it detects the [[Arrays#Strings|null byte]] at the end. 
`fgets()` terminates input lines by appending the [[Arrays#Strings|null byte]] to them.

For managing files of arbitrary data, including [[Arrays#Strings|null bytes]], a different function must be used.

```c
#include <stdio.h>
#include <stdlib.h>

void copyfile(char destination[], char source[])
{
    FILE        *fp_in   = fopen(source, "rb");
    FILE        *fp_out  = fopen(destination,  "wb");

//  ENSURE THAT OPENING BOTH FILES HAS BEEN SUCCESSFUL
    if(fp_in != NULL && fp_out != NULL) {

        char    buffer[BUFSIZ];
        size_t  got, wrote;

        while( (got = fread(buffer, 1, sizeof buffer, fp_in)) > 0) {  
            wrote = fwrite(buffer, 1, got, fp_out);
            if(wrote != got) {
                printf("error copying files\n");
                exit(EXIT_FAILURE);
            }
        }

    }

//  ENSURE THAT WE ONLY CLOSE FILES THAT ARE OPEN
    if(fp_in != NULL) {
        fclose(fp_in);
    }
    if(fp_out != NULL) {
        fclose(fp_out);
    }
}
```
