## Linux Redirections

### Bash is running provides these special files.

```
/dev/fd/fd
If fd is a valid integer, file descriptor fd is duplicated.

/dev/stdin
File descriptor 0 is duplicated.

/dev/stdout
File descriptor 1 is duplicated.

/dev/stderr
File descriptor 2 is duplicated.

/dev/tcp/host/port
If host is a valid hostname or Internet address, and port is an integer port number or service name, Bash attempts to open the corresponding TCP socket.

/dev/udp/host/port
If host is a valid hostname or Internet address, and port is an integer port number or service name, Bash attempts to open the corresponding UDP socket.
```

### noclobber
```
The noclobber option prevents you from overwriting existing files with the > operator.

Add the following line to .bashrc 
set -o noclobber
```

### Redirecting Input
```
[n]<word

word => read from this file
n => file descriptor which the contents of word passed to (std input (fd=0) is the default if n not specified)
```

### Redirecting Output
```
[n]>[|]word

word => write to this file
n => file descriptor whose contents passed (std output (fd=1) is the default if n not specified)
```

### Appending Redirected Output
```
[n]>>word

word => write to this file
n => file descriptor whose contents passed (std output (fd=1) is the default if n not specified)
```

### Redirecting Standard Output and Standard Error
```
&>word
or
>&word

Of the two forms, the first is preferred. This is semantically equivalent to
> word 2>&1
```

### Appending Standard Output and Standard Error
```
This construct allows both the standard output (file descriptor 1) and the standard error output (file descriptor 2) to be appended

&>>word
This is semantically equivalent to
>>word 2>&1

word => append to this file
```

### Here Documents
```
This type of redirection instructs the shell to read input from the current source until a line containing only word (with no trailing blanks) is seen.

[n]<<[-]word
        here-document
delimiter

"-" => if used leading tabs will be omitted
```

### Here Strings
```
[n]<<< word
```

### Duplicating File Descriptors
```
The redirection operator
[n]<&word
Is used to duplicate input file descriptors. If word expands to one or more digits, the file descriptor denoted by n is made to be a copy of that file descriptor.


The operator
[n]>&word
Is used similarly to duplicate output file descriptors. If n is not specified, the standard output (file descriptor 1) is used.
```

### Moving File Descriptors
```
[n]<&digit-
Moves the file descriptor digit to file descriptor n, or the standard input (file descriptor 0) if n is not specified. digit is closed after being duplicated to n.

[n]>&digit-
Moves the file descriptor digit to file descriptor n, or the standard output (file descriptor 1) if n is not specified.
```

### Opening File Descriptors for Reading and Writing
```
[n]<>word

Causes the file whose name is the expansion of word to be opened for both reading and writing on file descriptor n, or on file descriptor 0 if n is not specified. If the file does not exist, it is created.
```
