## Lab Report 1: Remote Access and FileSystem (Week 1)

In this lab report, I will share my experience with basic filesystem commands: `cd`, `ls`, and `cat`. Each command will be demonstrated with three examples:

1. Using the command with no arguments.
2. Using the command with a path to a directory as an argument.
3. Using the command with a path to a file as an argument.

## `cd` Command

### Example 1: No Arguments

```bash
cd

 
 1. Command with no arguments

* cd
* 
For this command, it will change the current directory to the home directory.

* ls
* 
This command will list all of the files and directories in the current directory. 

* cat
* 
When you run the "cat" command with no arguments it will cause it to read from standard input. This is not an error, but it might not be what you expect if you're used to using cat to read files.

 2. Command with a path to a directory as an argument

*cd

This command will change the current directory to the specified directory. The absolute path to the working directory when the command was run would be /path/to/directory.

*ls

This command will list all files and directories in the specified directory. The absolute path to the working directory when the command was run would be the directory you were in when you ran the command.

*cat

This command will result in an error because cat expects a file, not a directory. The error message will be something like cat: /path/to/directory: Is a directory.

 3. Command with a path to a file as an argument

*cd

This command will result in an error because cd expects a directory, not a file. The error message will be something like cd: not a directory: /path/to/file.

*ls

This command will display the file name. The absolute path to the working directory when the command was run would be the directory you were in when you ran the command.

*cat

This command will display the contents of the file. The absolute path to the working directory when the command was run would be the directory you were in when you ran the command.
