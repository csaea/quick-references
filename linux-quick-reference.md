# **Linux Quick Reference**

Quick reference for Linux fundamentals.

## Table of Contents
- [Common Commands](#common-commands)
- [File and Directory Management](#file-and-directory-management)
- [File Viewing and Manipulation](#file-viewing-and-manipulation)
- [Redirection](#redirection)

## Common Commands

Commonly used exit/interrupt commands. 

- `ctrl + c`: Halt current process and return to new command line.
- `quit`/`exit`/`logout`: Depends on context, will end current shell or session.

## File and Directory Management

Commands for navigating and managing files and directories.

- `ls`: List contents of current directory. Include hidden (-a) in long form (-l) or human-readable filesize (-h).
- `pwd`: Print Working Directory. Displays path of current directory.  
- `cd <directory>`: Change Directory to specified path.  
- `cd ..`: Return to previous or parent directory.  
- `mkdir <directory>`: Make new directory.  
- `touch <file>`: Create new file.
- `rm`: Remove file. Including all contents (-r) and forced (-f).
- `cp`: Copy. Including all contents (-r).
- `mv`: Move/rename.  

## File Viewing and Manipulation

Commands for viewing and manipulating file contents.

- `cat <file>`: Concatenates and outputs contents of file in terminal.  
- `less <file>`: Outputs contents of file separated into pages.  
- `head <file>`: Outputs first 10 lines of file.
- `tail <file>`: Outputs last 10 lines of file.
- `find`: Search. By file name (-name) or type (-type).

## Redirection

Commands for redirecting input and output.

- `>`: Direct output of a command into a file.  
  ```ex. echo "Hello, World!" > hello.txt```
- `>>`: Append the output of a command into a file.  
  ```ex. echo "Another line" >> hello.txt```
