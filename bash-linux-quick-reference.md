
# **Bash/Linux Quick Reference**

Quick reference for Bash/Linux commands. Bash (Bourne-Again Shell) is the default CLI shell on most Linux systems.

## Table of Contents
- [Common Shortcuts and Commands](#common-shortcuts-and-commands)
- [File and Directory Basics](#file-and-directory-basics)
- [File Viewing and Editing](#file-viewing-and-editing)
- [Output and Redirection](#output-and-redirection)
- [Variables](#variables)
- [Loops](#loops)
- [Conditionals](#conditionals)
- [Input](#input)
- [Search and Pattern Matching](#search-and-pattern-matching)
- [Network Utilities](#network-utilities)
- [Scripts](#scripts)
- [Common Options](#common-options)

---

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
- `rm <file>`: Remove file. Including all contents (-r) and forced (-f).
- `cp <file> <directory>`: Copy. Including all contents (-r).
- `mv <file> <new dir to move/same dir to rename>`: Move/rename.
- `date`: Retrieves date. 

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

## Variables

Variables are defined with a `variable name`, `=`, and `quotation marks` with no spaces between.  

- `$`: Used to reference the value of a variable.

```bash
 my_variable="Hello World"
 echo "$my_variable"    # With quotes - includes space and preserse content exactly.
 echo $my_variable      # Without quotes - may interpret space as a new argument!
 ```

### Variable Substitution 

When you want to include a variable or command in a string, use `$` or `$(...)`.

```bash
name="Alice"
echo "Hello, $name!"  # Output: Hello, Alice!

echo "Today's date is: $(date)"  # Output: Today's date is: Wed Nov 21 12:30:00 PST 2024

```

## Network Utilities 

- `ping`: Sends echo request to test/measure network connectivity of a host.
- `curl`: Client for URL. Get or send data (or files) from url protocols. Powered by libcurl.
- `wget`: Web Get. Download files from the web.
- `ssh`: Secure shell to remote machine.

## Loops 

Loops are primarily used to process many files, and generate reports. 

Loops follow the form:
```bash
for variable_name in directory/items; do
    {code block}
done
```
Example. The following code takes the content of every file in a directory and adds them into a single txt doc. 
```
for file in my_documents/*.txt; do
    cat "$file" >> output.txt
done
```

## Conditionals

### `if` Statement

Executes commands if a condition is true. It can be used with or without else statements.

**Syntax**:
```bash
if [ condition ]; then
    # commands
else
    # commands
fi

```

**Example**:
```bash
if [ -f "file.txt" ]; then
    echo "File exists!"
else
    echo "File does not exist."
fi

```

### `&&` (AND) and `||` (OR)

- `&&`: Run the second command if the first succeeds.
- `||`: Run the second command if the first fails.

**Examples**:
```bash
mkdir dir && cd dir
mkdir dir || echo "Exists"
```

---

## Input

- **`read`**: Accept input and store in a variable.  
  ```bash
  read variable_name
  ```

- **`read -p`**: Prompt the user before input.  
  ```bash
  read -p "Enter your name: " name
  ```

## Search and Pattern Matching

### grep
- `grep`: Global Regular Expression Print. Search for specific patterns within text. Filter text with regex. -i (case-insenstive) -c (count)
  
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

## Scripts 

Steps to create and run a script:

1. **Create the script**:
   ```bash
   nano myscript.sh
   ```

2. **Write the script** (e.g., add `echo "Hello, World!"`).

3. **Save and exit in nano**:
   - Press `Ctrl + O` to save.
   - Enter or confirm file name.
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

Options frequently used. Behavior varies depending on the specific command being used. Type `man <command>` to view the manual for each command.

- **`-h`**: Show help information (or human-readable sizes in some commands).
- **`-v`**: Verbose mode (or version in some commands).
- **`-f`**: Force action without confirmation (or overwrite).
- **`-r`**: Recursive (or reverse).
- **`-l`**: Long listing format.
- **`-a`**: Include hidden files (or all files).
- **`-t`**: Sort by modification time (or other criteria).
- **`-s`**: Display size in blocks (or summary).
- **`-C`**: Display count (or columns).
- **`-d`**: Show directory info.
- **`-q`**: Suppress warnings (or quiet mode).
- **`-n`**: Display numerical user/group IDs (or specify number).

---

  *Created by MD Harrell*  For more info about Linux commands, I suggest [this](https://ss64.com/bash/) resource.
