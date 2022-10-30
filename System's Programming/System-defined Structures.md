Created: 2022-09-22 12:57
Tags: #topic/programming 
Related: [[The Programming Language C]], [[operating systems]], [[structures]]

### Arrow Operator
```c
#include  <stdio.h>
#include  <time.h>

void greeting(void)
{
    time_t      NOW     = time(NULL);
    struct tm   *tm     = localtime(&NOW);

    printf("Today's date is %i/%i/%i\n",
             tm->tm_mday, tm->tm_mon + 1, tm->tm_year + 1900);

    if(tm->tm_hour < 12) {
        printf("Good morning\n");
    }
    else if(tm->tm_hour < 17) {
        printf("Good afternoon\n");
    }
    else {
        printf("Good evening\n");
    }
}
```
### Defining Our Own Datatypes
```c
//  DEFINE THE LIMITS ON PROGRAM'S DATA-STRUCTURES
#define MAX_TEAMS               24
#define MAX_TEAMNAME_LEN        30
....

typedef struct {
    char    teamname[MAX_TEAMNAME_LEN+1];        // +1 for null-byte        
    ....
    int     played;
    ....
} TEAM;

TEAM    team[MAX_TEAMS];

//  PRINT EACH TEAM'S RESULTS, ONE-PER-LINE, IN NO SPECIFIC ORDER
for(int t=0 ; t<nteams ; ++t) {
    TEAM    *tp = &team[t];

    printf("%s %i %i %i %i %i %i %.2f %i\n", // %age to 2 decimal-places
            tp->teamname,
            tp->played, tp->won, tp->lost, tp->drawn,
            tp->bfor, tp->bagainst,
            (100.0 * tp->bfor / tp->bagainst),      // calculate percentage
            tp->points);
}
```

### Finding Attributes of a File
```c
#include  <stdio.h>
#include  <stdlib.h>
#include  <sys/types.h>
#include  <sys/stat.h>
#include  <time.h>
#include  <unistd.h>

char *progname;

void file_attributes(char *filename)
{
  struct stat  stat_buffer;

  if(stat(filename, &stat_buffer) != 0) {  // can we 'stat' the file's attributes?
    perror( progname );
    exit(EXIT_FAILURE);
  }
  else if( S_ISREG( stat_buffer.st_mode ) ) {
    printf( "%s is a regular file\n", filename );
    printf( "is %i bytes long\n", (int)stat_buffer.st_size );
    printf( "and was last modified on %i\n", (int)stat_buffer.st_mtime);

    printf( "which was %s", ctime( &stat_buffer.st_mtime) );
  }
}
```

### Reading the Contents of a Directory
```c
#include  <stdio.h>
#include  <sys/types.h>
#include  <sys/stat.h>
#include  <sys/param.h>
#include  <dirent.h>
#include  <unistd.h>

**void** list_directory(**char** *dirname)
{
    **char**  fullpath[MAXPATHLEN];

    .....
    **while**((dp = readdir(dirp)) != NULL) {
        ****struct** stat  stat_buffer**;
        ****struct** stat  *pointer = &stat_buffer**;

        sprintf(fullpath, "%s/%s", dirname, dp->d_name );

        **if**(**stat(fullpath, pointer)** != 0) {
             perror( progname );
        }
        **else if**( **S_ISDIR( pointer->st_mode )**) {
            printf( "%s is a directory\n", fullpath );
        }
        **else if**( **S_ISREG( pointer->st_mode )**) {
            printf( "%s is a regular file\n", fullpath );
        }
        **else** {
            printf( "%s is unknown!\n", fullpath );
        }
    }
    closedir(dirp);
}
```