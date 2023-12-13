simple-c-shell
==============

Simple and thoroughly commented shell written in C, just for educative purposes. 

Created by [Kevin Ochola](http://kevinocholah.wixsite.com/2023) as Software Engineering Project exercise, and released under GPLv3.

Features
--------
* In order to retrieve the current process’ ID, use the system call getpid
* Basic commands: `exit`, `ls`, `clear` and `cd`
* Environment management with `setenv` and `unsetenv`
* Program invocation with forking and child processes
* Background execution of programs with `&`
* SIGINT signal when Ctrl-C is pressed (shell is not exited)
#	Arguments
The command line arguments are passed through the main function: int main(int ac, char **av);

av is a NULL terminated array of strings
ac is the number of items in av
av[0] usually contains the name used to invoke the current program. av[1] is the first argument of the program, av[2] the second, and so on.

# Executing a program
The system call execve allows a process to execute another program (man 2 execve). Note that this system call does load the new program into the current process’ memory in place of the “previous” program: on success execve does not return to continue the rest of the “previous” program.

# Creating processes
The system call fork (man 2 fork) creates a new child process, almost identical to the parent (the process that calls fork). Once fork successfully returns, two processes continue to run the same program, but with different stacks, datas and heaps.

# File information
The stat (man 2 stat) system call gets the status of a file. On success, zero is returned. On error, -1 is returned.


