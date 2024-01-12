# `cd` Command

## No arguments:
```
[user@sahara /]$ cd
[user@sahara ~]$
```
This appears to always change the working directory to /home (denoted by ~), no matter what the starting directory is. This is the default behavior of the `cd` command.
The working directory at the start of the code is `/`, or the root directory.
This is not an error.


## Directory argument:

```
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$
```
Using 'cd' with a directory changes the current working directory to the specified directory, as is the purpose of the command. By running `cd lecture1`, the directory changes from the `home` directory to `home/lecture1/`
The working directory at the start of the code is `~`, or `/home`.
This is not an error.

## File argument:

```
[user@sahara ~]$ cd lecture1/Hello.java
bash: cd: lecture1/Hello.java: Not a directory
```

Using the `cd` command with a file argument results in an error.  This is because the purpose of the command is to change the working
directory to the directory in the argument, which is only possible if the argument is a directory.
The working directory at the start of the code is `~`, or `/home`.

# `ls` Command

## No arguments:
```
[user@sahara ~]$ ls
lecture1
```
With no arguments, this command just lists out all files/directories in the current working directory. The output of the command is the content of the `/home` directory, which is just `/home/lecture1`. 
The working directory at the start of the code is `~`, or `/home`.
This is not an error.

## Directory argument:
```
[user@sahara ~]$ ls lecture1/
Hello.class  Hello.java  messages  README
```
With a directory passed as an argument, the command lists out all files/directories in the directory provided. The output of the command are the contents within the `/home/lecture1/` directory.
The working directory at the start of the code is `~`, or `/home`.
This is not an error.

## File argument:
```
[user@sahara ~]$ ls lecture1/Hello.java 
lecture1/Hello.java
```
When a file is provided as an argument, the output is just the path for that file.
The working directory at the start of the code is `~`, or `/home`.
This is not an error.

# `cat` Command

## No arguments:
```
[user@sahara ~/lecture1]$ cat

```
With no arguments, the `cat` command waits for the user to input content before printing out what the user inputted.
The working directory at the start of this code is `/home/lecture1/`.
This is not an error.

## Directory argument:
```
[user@sahara ~/lecture1]$ cat messages/
cat: messages/: Is a directory
```
With a directory as an argument, the command produces an error informing us that the path leads to a directory. 
The command does not complete its intended purpose of printing the contents of one or more files. This is because the command is not meant to be used on directories.
The working directory at the start of this code is `/home/lecture1/`.

## File argument:
```
[user@sahara ~/lecture1]$ cat README 
To use this program:

javac Hello.java
java Hello messages/en-us.txt
```
With a file as an argument, the command prints out the contents of that file. This is because the `cat` command is used to print out (and concatenate) the contents of one or more files.
The contents of the `README` file are exactly the contents that the command produced.
The working directory at the start of this code is `/home/lecture1/`.
This is not an error.

