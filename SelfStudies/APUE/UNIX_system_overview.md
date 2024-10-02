OS can be defined as the software the controls hardware resources of the computer, and provides an environment under which programs can run.

**kernel**: this software.

**system calls**: interface to the kernel


## logging in

### login name

>example of entry in password file:\
>sar:X:205:105:Stephen:/home/sar:/bin/ksh

login name, encrypted password, numeric user ID, numeric group ID, comment field, home directory and shell program.

### shells

**Shell**: command-line interpreter that reads uder input and executes commands\
User input normally from terminal or sometimes from a file.


## Files and Directories

### file system

**root**: everything starts from it. name: /.

**directory**

...
Pathname, working dir, home dir


## Input and Output

Standard i/o and error, unbuffered io, standard io

## Programs and processes

**program**: executable file residing on disk

**Process control**\
three primary functions: fork, exec, waitpid

**threads and thread ids**


## Eroor handling

errno; strerror; perror;

errors in <errno.h> divided into two categories: fatal and non-fatal;

## User ID
user whos userid is 0 is root or the superuser

**group ID**
groups normally used to collect users together into projects/departments;

## signals
signals are a tecnique used to notify a process that some condition has occured

## time valuess 
...


## System calls ana Library functions

All implementations of the UNIX system provide a well-defined, limited number of entry points directly into the kernal called **service calls**


