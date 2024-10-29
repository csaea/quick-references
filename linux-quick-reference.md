# **Linux Quick Reference**

Quick reference for Linux Commands.

## Table of Contents
- [Directories and Files](#directories-and-files)

## Directories and Files 

Commands to help navigate directories.

Sure! Here’s the condensed list with examples on the same line:

### Commands to Help Navigate Directories

- `pwd`: Print Working Directory. Displays path of current directory.  
  *Example:* `pwd` → `/home/user/documents`
  
- `cd <directory>`: Change Directory to specified path.  
  *Example:* `cd projects`
  
- `cd ..`: Return to previous or parent directory.  
  *Example:* `cd ..`
  
- `ls`: List contents of current directory.  
  *Example:* `ls` → `file1.txt file2.txt projects`
  
- `ls -la`: List including hidden files.  
  *Example:* `ls -la` → `drwxr-xr-x 3 user user 4096 Oct 29 12:00 .`
  
- `mkdir <directory>`: Make new directory.  
  *Example:* `mkdir new_folder`
  
- `touch <file>`: Create new file.  
  *Example:* `touch newfile.txt`
  
- `cat <file>`: Concatenates and outputs contents of file in terminal.  
  *Example:* `cat file1.txt`
  
- `less <file>`: Outputs contents of file separated into pages.  
  *Example:* `less file1.txt`
  
- `head <file>`: Outputs first 10 lines of file.  
  *Example:* `head file1.txt`
  
- `>`: Direct output of a command into a file.  
  *Example:* `echo "Hello, World!" > hello.txt`
  
- `>>`: Append the output of a command into a file.  
  *Example:* `echo "Another line" >> hello.txt`

## File Listing

```bash
-rw-r--r-- 1 alice staff 2048 Oct 29 14:30 example.txt
```

This line provides a  overview of a regular file, including permissions, ownership, size, modification time, and filename.

### Breakdown:

- **`-rw-r--r--`**: 
  - **`-`**: Regular file (not a directory).
  - **`rw-`**: Owner (alice) has read and write permissions.
  - **`r--`**: Group (staff) has read permissions only.
  - **`r--`**: Others have read permissions only.

- **`1`**: Number of hard links to the file.

- **`alice`**: Owner's name.

- **`staff`**: Group name.

- **`2048`**: Size of the file in bytes.

- **`Oct 29 14:30`**: Last modified date and time.

- **`example.txt`**: Name of the file.


