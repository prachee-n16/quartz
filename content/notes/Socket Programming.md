---
title: Socket Programming
tags:
  - SocketProgramming
  - C
  - to-complete
---
- **Sockets** allow for Inter-Process Communication (IPC) between two different processes on same/different machines. 
- **Socket Programming** is connecting two nodes on a network so they can communicate.
	- **Server** socket will listen on a port at an IP, and service requests it receives from clients
	- **Client** socket reaches out to make a connection, and sends requests. 
![](https://media.geeksforgeeks.org/wp-content/uploads/20220330131350/StatediagramforserverandclientmodelofSocketdrawio2-448x660.png)

- `socket()` involves creating the socket, `bind()` will binds the newly created socket to an address and port
- If the server socket is not put into passive mode with `listen()`, it will lead to an error
	- A server will queue certain number of clients, before returning `ECONNREFUSED`
- `accept()` extracts first request in queue and establishes connection

The above model assumes server handles one client at a time. What about multiple clients?
- Option 1: Multi-threading but it's not a good idea
	- Unpredictable results with threading
	- Overhead switching of context
	- Deadlocks can occur 
- Option 2: using **select()** command which is much better
	- The clients are 'file descriptors' and the socket waits for one of them to be activated
	- Select works like an [[Interrupts and System Calls|interrupt handler]], where it activates when a file descriptor sends data

Reference: 
- https://www.geeksforgeeks.org/socket-programming-cc/
- https://www.geeksforgeeks.org/socket-programming-in-cc-handling-multiple-clients-on-server-without-multi-threading/
