# **Linux Quick Reference**

Quick reference for Linux fundamentals.

## Table of Contents
- [Exit Commands](#exit-commands)
- [File and Directory Basics](#file-and-directory-basics)
- [File Viewing and Editing](#file-viewing-and-editing)
- [Output and Redirection](#output-and-redirection)
- [Search and Pattern Matching](#search-and-pattern-matching)
- [Network Utilities](#network-utilities)
- [Loops](#loops)
- [Common Options](#common-options)

## Exit Commands

Commonly used exit/interrupt commands. 

- `ctrl + c`: Halt current process and return to new command line.
- `quit`/`exit`/`logout`: Depends on context, will end current shell or session.

## File and Directory Basics

Commands for navigating and managing files and directories.

- `ls`: List contents of current directory. Include hidden (-a) in long form (-l) or human-readable filesize (-h).
- `pwd`: Print Working Directory. Displays path of current directory.  
- `cd <directory>`: Change Directory to specified path.  
- `cd ..`: Return to previous or parent directory.  
- `mkdir <directory>`: Make new directory.
- `rmdir <directory>`: Delete directory
- `touch <file>`: Create new file.
- `rm`: Remove file. Including all contents (-r) and forced (-f).
- `cp`: Copy. Including all contents (-r).
- `mv`: Move/rename.  

## File Viewing and Editing

Commands for viewing and manipulating file contents.

- `cat <file>`: Concatenates and outputs contents of file in terminal.  
- `less <file>`: Outputs contents of file separated into pages.  
- `head <file>`: Outputs first 10 lines of file.
- `tail <file>`: Outputs last 10 lines of file.
- `find`: Search. By file name (-name) or type (-type).
- `open <file>`: Opens file outside terminal.
- `nano <file>`: Edit file. Requires nano installed.

## Output and Redirection

Commands for output to terminal, and redirecting input and output.

- `echo`: display message or variable value to terminal 
- `>`: Direct output of a command into a file.  
  ```ex. echo "Hello, World!" > hello.txt```
- `>>`: Append the output of a command into a file.  
  ```ex. echo "Another line" >> hello.txt```
- `<`: Direct input from a file to a command.  
  ```ex. sort < unsorted.txt```
- `|`: Pipe the output of one command as input to another command.  
  ```ex. ls -l | grep "txt"```

## Search and Pattern Matching

### grep
- `grep`: Global Regular Expression Print. Filter text with regex. -i (case-insenstive) -c (count)
  
#### Examples:
```bash
# search for word "error" in file:
grep "error" logfile.txt

# count how many occurences of word "success" in file:
grep -c "success" logfile.txt
```

### awk
- `awk`: As a command `awk` filters, processes, analyzes text in files, for pattern-matching, field manipulation, and user-defined outputs.
*Works best with structured text files, like .csv, log files, etc.*
#### Examples
```bash
# Print first field of file (by default fields are seaparted by a space): 
awk '{print $1}' data.txt

# Filter lines whose second column value is greater than 50 
awk '$2 > 50' data.txt
```

## Network Utilities 

- `ping`: Sends echo request to test/measure network connectivity of a host.
- `curl`: Client for URL. Get or send data (or files) from url protocols. Powered by libcurl.
- `wget`: Web Get. Download files from the web.
- `ssh`: Secure shell to remote machine.

## Loops 

Loops are primarily used to process many files, and generate reports. 

Loops follows the form:
```bash
for variable in items; do
    {code block}
done
```
#### Example
```
# The following code 
# 1) loops over every .txt file in the my_documents directory
# 2) runs `cat` on every file, redirecting the output to a new text file.

for file in my_documents/*.txt; do
    cat "$file" >> output.txt
done
```

## Common Options 

Common Options

- **`-h`**: Help.
- **`-v`**: Verbose. Displays more details.
- **`-f`**: Force action without confirmation.
- **`-r`**: Recursive. Applys command to all contents in a directory.
- **`-l`**: Listing format (long).
- **`-a`**: Include hidden files.
- **`-t`**: Time. Sort by last modified. 
- **`-s`**: Display size of files in blocks.
- **`-C`**: Display output in columns.
- **`-d`**: Show directory information instead of contents.
- **`-q`**: Suppress warnings or other non-critical output.
- **`-n`**: Numerical user and group IDs instead of names.
- **`--version`**: Show version information for a command.

  ----

  *Created by Mr Harrell*  For more info about Linux commands, I suggest [this](https://ss64.com/bash/) resource.
