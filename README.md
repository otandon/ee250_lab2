# Lab 2

## Team Members
- Om Tandon

## Lab Sheet Question Answers
Question 1: 
1
4
9
1
2
4
6
1
2
3
6
7
8
9
This is what outputted when I did the sequence 3 times. When the loss was
introduced, UDP became unreliable. Several numbers from the sequence were
missing. This occurred because UDP is a connectionless protocol that does not
provide acknowledgements, retransmissions, or ordering guarantees. When packets
were lost due to simulated network loss, UDP did not attempt to recover them,
resulting in incomplete data delivery


Question 2:
When the loss was introduced, TCP stayed reliable and in order (no numbers skipped). However, the speed of the communication decreased, with delays and 
even occasional stalls before data was delivered. In some cases, the co nection
seemed to hang or terminate before completing the full sequence. This is because TCP uses acknowledgements and retransmissions to guarantee reliable delivery.
Under high loss, TCP must repeatedly retransmit lost packages and reduce its
congestion window, which increases latency and can lead to timeouts or stalled 
connections.


## Server Code Questions and Answers

Question 1:
argc: argument count, number of command line arguments passed to program
arvgv[]: argument vector that contains the strings containing those args

Question 2:
UNIX file descriptor is a non-negative integer that uniquely identifies an open file, socket, or I/O resource within a process. File descriptor table is maintained by the OS, maps file descriptors to open files or sockets. Sockets are treated like files in UNIX.

Question 3:
Struct is a data type that groups related variables under one name.

sockaddr_in is a structure used to represent an IPv4 socket address. Contains, sin_famiily (address family), sin_port (port number), sin_addr (IP address), sin_zero (padding).

Question 4:
Input parameters: domain (address family), type (socket type), protocol
Return value: returns a file descriptor for the socket if success, -1 if error

Question 5:

Bind input parameters: sockfd (socket file descriptor), addr (pointer to socket address structure), addrlen (size of the address structure)

listen input parameters: sockfd (socket file descriptor), backlog (max number of pending connection requests)

Question 6:
while(1) keeps server running indefinitely so it can accept multiple connections over time. In this case, the server only handles one connection at a time. So if multiple connections happen simultaneously, then new connections must wait, preventing server scaling and blocking other clients if one is slow.

Question 7:
fork() creates a new child process that is a copy of the parent process.For this case, the parent process continues accepting new connections, while each child process handles one client connection. This allows the server to handle multiple clients concurrently, improving the scalability. 

Question 8:
System call: controlled way for user-level program to request services from the operating system kernel. Allow programs to perform privileged operations like networking and I/O safely. 
