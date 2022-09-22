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
