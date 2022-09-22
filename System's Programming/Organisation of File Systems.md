# Organisation of File Systems
Created: 2022-09-19 17:05
Tags: #topic
Related: [[Operating Systems]]

### Concepts
**fields** - represent the smallest logical item of data, e.g. single integers of strings
**records** - consist of one or more fields and are treated as a single unit
**files** - collections of identically represented records, accessed by unique names
**databases** - consist of one or more files whose contents are strongly related

### File Management System
#### File Creation/Deletion
`open()`, `creat()`, `close()`, `truncate()`, `unlink()`

#### Accessing a File's Contents
`read()`, `write()`, `lseek()`

#### Accessing a File's Attributes
`chmod()`, `chmown()`, `stat()`

### Components of the File Management System
#todo/excalidraw 19 Sep 27.30
**device drivers** - communicate directly with I/O hardware
**basic file system** - exchanges fixed-sized pieces of data with the device drivers
**I/O supervisor** - manages the choice of device
**logical I/O layer** - maps I/O request to blocks

### Role of Directory Structures
#todo/excalidraw 47 min
Holds the metadata for files. Half of this metadata is common to all file systems, while others are specific to certain file systems.

### File Allocation
#### Contiguous
Requires the file's maximum size to be determined when the file is created.
The *file allocation table* stores a file's starting block and length.
Method suffers from internal fragmentation (in the initial allocation is too large) and external fragmentation (as files are deleted over time).

#### Chained
[[lists#singly-linked-representation]]of block allocation. New blocks may be allocated on any free block on the disk, meaning the blocks don't need to be contigous.

A small pointer of 32 or 64 bits is allocated to indicate where the next block in the chain is.

#### Indexed
Method of choice for Unix and Windows. Like **inodes** #todo, the file-allocation table contains a multi-level index for each file.
This multi-level index contains direct pointers to data blocks, and pointers to indirection blocks (which point to more data blocks).
