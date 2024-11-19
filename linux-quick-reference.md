# **Linux Quick Reference**

Quick reference for Linux fundamentals.

## Table of Contents
- [Common Shortcuts and Commands](#common-shortcuts-and-commands)
- [File and Directory Basics](#file-and-directory-basics)
- [File Viewing and Editing](#file-viewing-and-editing)
- [Output and Redirection](#output-and-redirection)
- [Search and Pattern Matching](#search-and-pattern-matching)
- [Network Utilities](#network-utilities)
- [Loops](#loops)
- [Variables](#variables)
- [Input](#input)
- [Scripts](#scripts)
- [Common Options](#common-options)


## Common Shortcuts and Commands

- **`Ctrl + C`**: Terminate current process.  
- **`Tab`**: Autocomplete file or command name.  
- **`Up/Down Arrow`**: Cycle through command history.  
- **`Ctrl + A`**: Move cursor to the beginning of the line.  
- **`clear` or `Ctrl + L`**: Clear terminal screen.
- **`man`**: displays **man**ual documentation for a command. 
- **`q`/`quit`/`exit`/`logout`**: End current shell or session, depending on context.

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
for variable_name in directory/items; do
    {code block}
done
```
#### Example
```
# The following code takes the content of every file in a directory and adds them into a single txt doc. 

for file in my_documents/*.txt; do
    cat "$file" >> output.txt
done
```

## Variables

Variables are defined with a `variable name`, `=`, and `quotation marks` with no spaces between. Single quotation marks for literal interpretation, double for dynamic substitution. 

- `$`: Used to reference the value of a variable.

  ```bash
  my_variable="Hello"
  echo $my_variable
  ```

### Environment Variables

Built-in (predefined) variabless containing info about the system. Uppercase. You can create custom ENV variables, too. 

- **`printenv`**: Display all environmental variables. 
- **`$HOME`**: Current user's home directory.
- **`$USER`**: Current logged-in username.
- **`$PATH`**: Directories to search for executable files.
- **`$PWD`**: Current working directory.
- **`$EDITOR`**: Default text editor (e.g., `nano`, `vim`).

---

## Input

## Accepting Input

- **`read`**: Accept input and store in a variable.  
  ```bash
  read variable_name
  ```

- **`read -p`**: Prompt the user before input.  
  ```bash
  read -p "Enter your name: " name
  ```

## Scripts 

Steps to create and run a script:

1. **Create the script**:
   ```bash
   nano myscript.sh
   ```

2. **Write the script** (e.g., add `echo "Hello, World!"`).

3. **Save and exit in nano**:
   - Press `Ctrl + O` to save.
   - Press `Ctrl + X` to exit.

4. **Make it executable**:
   ```bash
   chmod +x myscript.sh
   ```

5. **Run the script**:
   ```bash
   ./myscript.sh
   ```

## Common Options 

Common Options, often different depending on command. Type `man` then a command to receive a command's manual. 

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
