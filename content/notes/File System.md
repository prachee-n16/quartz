---
title: File System
enableToc: false
tags:
  - C
  - Areas
  - OperatingSystems
  - completed
  - ece252
---
**File System**
The file system provides organization for the files through a directory structure + maintains metadata related to files.

In UNIX, "everything is a file"
- TODO: Look into: https://tldp.org/LDP/sag/html/dev-fs.html
- An area of disk is designates as belonging to a file, and file is just a logical unit to organize this.

Files have the following attributes:
- Name
- Identifier: numerical value that serves as a unique identifier for the file within the file system (find this for a file)
	- there is not much of a difference between this and name
- Type
	- in most OS, any program can open arbitrary files and the extensions are just a suggestion. 
- Location
- Size
- Protection
- Time, Date, User ID

QNX (OS provided by Blackberry) - primarily used in embedded systems
- files are maintained in a structure. Directories are really just like files, information about what files are where, and they are also being stored on disks

Six basic file ops:
1. Creating a file [Go to Section](#create)
2. Writing a file [Go to Section](#write)
3. Reading a file [Go to Section](#read)
4. Reposition within a file [Go to section](#seek)
5. Delete a file  [Go to section](#delete)
6. Truncate a file  [Go to section](#delete)
#### create
(by extension write/read)
fopen will call open on a file - When running Windows, it actually runs openFileEx() under the hood. We don't really need to care since it abstracts this from us. The UNIX system libraries use an integer instead of a FILE*.
- FILE* is an access to the file apparently? access point to a file or an input/output stream rather than the file or stream itself

In addition to the filename as the first parameter, the function is called with the mode as the second parameter.
- **"r" (Read)**: Opens a file for reading.
- **"w" (Write)**: Opens a file for writing.
- **"a" (Append)**: Opens a file for writing, but if the file exists, it appends data to the end rather than truncating it.
- **"r+" (Read and Write)**: Opens a file for both reading and writing
- **"w+" (Write and Read)**: Opens a file for both reading and writing
- **"a+" (Append and Read)**: Opens a file for both reading and writing. If the file doesn't exist, it creates a new file. If it exists, it appends data to the end.
- "x" (new to C): create a new file safely without risking the unintentional overwriting of an existing file
If you add b to the end, like `rb` then we are reading in binary mode. Mostly irrelevant.
#### seek
- Repositioning is also called a seek, done in C with the `fseek()` call which adjusts pointer for reading or writing
- you can go to any arbit. character so it's actually kind of dangerous and we can not call this op if a file is opened for append
- passing a negative number will move you backwards/
#### delete
- In C, a file is deleted with the remove() function because this simple program deletes whatever file is provided as the second argument.
Truncating can only be done with the UNIX libraries using either truncate() or ftruncate().
#### write
- writing is easy because it works like printf, actual function call is just called `fprintf` 
#### read
- Reading from a file involves the use of fscanf which is a mirror image of fprintf

A directory is a symbol table that translates file name to directory entries. Typically support the below operations
- search
- list directory
- navigate file system
- add and remove and rename file
Tree-structured: there is a root directory, and every file in the system has a unique name when the name and path to it (from the root) are combined.

File systems may also support the sharing of files. There is one copy of the file but it has more than one name. In UNIX this is called a link and this is effectively a pointer to another file.
- Symlinks, or symbolic links, are just references by file name.
- Creating a hardlink is creating a pointer to the underlying file in the file system.
- If a hardlink exists and the user deletes that file, the file still remains on disk until last hardlink is removed

Also: [[File Access Mechanisms in Filesystems]]