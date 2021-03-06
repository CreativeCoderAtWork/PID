# PID
C program for Pid manager
An operating system’s pid manager is responsible for managing process

identifiers. When a process is first created, it is assigned a unique pid

by the pid manager. The pid is returned to the pid manager when the

process completes execution, and the manager may later reassign this

pid. Process identifiers are discussed more fully in Section 3.3.1. What

is most important here is to recognize that process identifiers must be

unique; no two active processes can have the same pid.

Use the following constants to identify the range of possible pid values:

#define MIN PID 300

#define MAX PID 5000

You may use any data structure of your choice to represent the availability

of process identifiers. One strategy is to adopt what Linux has

done and use a bitmap in which a value of 0 at position i indicates that

a process id of value i is available and a value of 1 indicates that the

process id is currently in use.

Implement the following API for obtaining and releasing a pid:

• int allocate map(void)—Creates and initializes a data structure

for representing pids; returns—1 if unsuccessful, 1 if successful

• int allocate pid(void)—Allocates and returns a pid; returns—

1 if unable to allocate a pid (all pids are in use)

• void release pid(int pid)—Releases a pid
