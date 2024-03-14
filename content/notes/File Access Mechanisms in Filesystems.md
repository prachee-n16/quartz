---
title: File Access Mechanisms in Filesystems
tags:
  - OperatingSystems
  - Areas
  - completed
---
Files usually have some permissions associated with them: 
- Read
- Write
- Execute
- Append (write at the end of the file)
- Delete
- List (view the attributes of the file)

**Access control**
- permissions can be assigned for: Owner, Group, Everyone
- Three basic permissions: R, W, Execute
	- permissions are represented by 10 bits where 1 indicates true, 0 indicates false
- first bit is directory bit.
	- Next three are read, write, execute for the owner. 
	- Then read, write, execute for the group. 
	- Finally, read, write, execute for everyone.

The permissions can be shown in a human-readable format.
- The character d is used to indicate a directory. 
- r to indicate read access. 
- w to indicate write access. 
- x to indicate execute access

**File Locks**
- Some OS supports file locks which can be exclusive or non-exclusive
	- When a file is locked by a process, other processes can't open that file (see a failure)
	- It also can not be deleted when it is being used by a program
- Windows uses locking: any file open in an program can't be deleted but UNIX does not
	- as long as program remains open, retaining ref to file, it can still operate on file
To lock a file in Linux, the call for this is flock()
A shared lock would be LOCK_SH, and to unlock the parameter is LOCK_UN
- Non-exclusive file locks (also known as shared locks or read locks) allow multiple processes or threads to access a file simultaneously for reading purposes
- Exclusive file locks (also known as write locks or exclusive locks) provide exclusive access to a file to the process or thread that holds the lock