# Operating System Users and Groups
Created: 09/10/2022 at 20:07
Tags: #topic/software 
Related: [[Operating Systems]]

### Users and their OS Representation
[[OS Services|System calls]] should be the only mechanism by which a process interacts with the OS,

Unix has adopted the approach that processes are the only active entities on a system.

### User IDS
Called *uids* it is a 16-bit unsigned identifier. It is established when logging into a Unix system.

We can change and determine the uid with `setuid()` and `getuid()`.


#### Effective UID
Most of the time the *uid* and the effective *uid* is the same, and in programs, they always check the effective *uid*.

#### Incorrect Use?
Unix also uses distinct userids to represent activities and programs. Shutdown, mail, news are typically set to small userids.

#### The Superuser
Unix uses the special userid value of 0 to represent the root account or superuser

#### `chroot`
Changes the root of the file system.

### Groups of Users
 Each user is also represented by group identifiers, or groupids. This means multiple users can share files that way.
```c
#include <stdio.h>
#include <unistd.h>
#include <grp.h>

#define MY_MAXGROUPS   100

**void** print_my_groups(**void**)
{
    gid_t groups[MY_MAXGROUPS];

    **int** ngroups = **getgroups(MY_MAXGROUPS, groups)**;

    **for**(**int** g=0 ; g<ngroups ; ++g) {
        **struct group *gp    = getgrgid(groups[g])**;

        **if**(gp != NULL) {
            printf("gid: %-8i name: %s\n", groups[g], **gp->gr_name**);

            printf("\tmembers:");
            **for**(**int** m=0 ; **gp->gr_mem[m]** != NULL ; ++m) {
                printf(" %s", **gp->gr_mem[m]**);
            }
            printf("\n\n");
        }
    }
}
```

### Changing and Setting User Information
A process can changes the userid for the life of the program so when someone runs it, they can access the required files.