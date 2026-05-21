# Bash Tutorial - Text Processing

## Bash `grep` Command - Search Text Using Patterns

### Using the `grep` Command

The `grep` command is used to search for text patterns within files.

It's a powerful way to find specific text in large files or across many files.

### Basic Usage

```bash
grep 'pattern' filename
```

### Options

- `-i` - Search ignoring case differences (uppercase or lowercase)
- `-r` - Search through all files in a directory and its subdirectories
- `-v` - Find lines that do not match the pattern

### Ignore Case

### Recursive Search

### Invert Match

### Using `grep` with Regular Expressions

Regular expressions allow you to search for complex patterns.

Finds lines starting with a letter:

```bash
grep '^[A-Za-z]' file.txt
```

## Bash `awk` - Pattern Scanning and Processing Language

### Using the `awk` Command

The `awk` command is used for pattern scanning and processing language.

It's useful for handling text files and used for data extraction and reporting.

All examples below use the example_data.csv file:

```
id,Created,Amount,Currency,Description,Customer
1,2024-11-01,100,USD,Payment,John Doe
2,2024-11-02,200,EUR,Refund,Jane Smith
3,2024-11-03,150,USD,Purchase,Emily Davis
4,2024-11-04,175,GBP,Subscription,Michael Brown
```

- To print the first column of a file, use `awk -F"," '{print $1}' filename`.

### Options

- `-F` - Set what separates the data fields
- `-v` - Set a variable to be used in the script
- `-f` - Use a file as the source of the awk program

### Field Separator

### Assign Variable

The `-v` option lets you assign a variable to be used within the awk script.

```bash
awk -F"," -v var="Amount:" '{print var, $3}' example_data.csv
# Output:
# Amount: Amount
# Amount: 100
# Amount: 200
# Amount: 150
# Amount: 175
```

### Using `awk` for Data Manipulation

Awk can perform complex data manipulation tasks.

```bash
# calculates the sum of the Amount column:
awk -F"," '{sum += $3} END {print sum}' example_data.csv
# Output:
# 625
```

### Common Errors and Troubleshooting

## Bash `sed` Command - Stream Editor

### Using the `sed` Command

The `sed` command is a stream editor used to perform basic text transformations on an input stream (a file or input from a pipeline).

It's a powerful tool for making quick edits to files or streams of data.

All examples below use the `example_text.txt` file:

```
Hello World
Line 1
Line 2
```

### Basic Usage

```bash
sed 's/pattern/replacement/' filename
```

```bash
sed 's/World/Bash/' example_text.txt
Hello Bash
Line 1
Line 2
```

### Options

- `-i` - Edit files directly without needing to save separately
- `-e` - Add the script to the commands to be executed
- `-n` - Don't automatically print lines
- `-r` - Use extended regular expressions
- `-f` - Add script from a file
- `-l` - Specify line length for l command

### Edit Files In Place

```bash
sed -i 's/World/Bash/g' example_text.txt
cat example_text.txt
# Hello Bash
# Line 1
# Line 2
```

### Suppress Printing

The `-n` option suppresses automatic printing of pattern space.

By default, sed prints each line of input to the output. Using `-n` allows you to control which lines are printed, typically with the `p` command.

```bash
sed -n 's/World/Bash/p' example_text.txt
# Hello Bash
```

### Extended Regular Expressions

The `-r` option allows the use of extended regular expressions, which provide more powerful pattern matching capabilities than basic regular expressions.

Without this option, `sed` uses basic regular expressions.

```bash
sed -r 's/(World|Line)/Hello/g' example_text.txt
# Hello Hello
# Hello 1
# Hello 2
```

### Script from a File

The `-f` option allows you to add a script from a file, which is useful for executing complex or multiple sed commands.

Content of `script.sed` file:

```
s/World/Bash/g
```

```bash
sed -f script.sed example_text.txt
# Hello Bash
# Line 1
# Line 2
``` 

### Specify Line Length

The `-l` option specifies the line length for the `l` command, which prints lines with non-printable characters.

This option is useful for formatting output when dealing with long lines.

```bash
sed -l 10 'l' example_text.txt
# Hello Wor\
# ld$
# Hello World
# Line 1$
# Line 1
# Line 2$
# Line 2
```

### Redirect Output to a File

To save the changes made by `sed` to a file, you can redirect the output to a new file. This is useful when you don't want to overwrite the original file.

```bash
sed 's/World/Bash/' example_text.txt > new_example_text.txt
cat new_example_text.txt
# Hello Bash
# Line 1
# Line 2
```

### Using `sed` for Advanced Text Processing

Adds a prefix to each line:

```bash
sed 's/^/Prefix: /' example_text.txt
# Prefix: Hello World
# Prefix: Line 1
# Prefix: Line 2
```

### Common Errors and Troubleshooting

## Bash `cut` Command - Remove Sections from Lines

### Using the `cut` Command

The `cut` command is used to remove sections from each line of files.

It's a useful tool for extracting specific fields of data from a file or output stream.

All examples below use the `example_data.txt` file:

```
Kai 	Refsnes	30,Norway
Robin	Smith	25,Denmark
Sienna	Davis	40,Germany
```

### Basic Usage

To extract the first field of a file, use `cut -f1 filename`:

```bash
cut -f1 example_data.txt
# Kai
# Robin
# Sienna
```

By default, `cut` uses a tab as the delimiter.

### Options

- `-d` - Choose what separates the fields
- `-f` - Select specific fields to display
- `--complement` - Show all fields except the selected ones

### Specify Delimiter

```bash
cut -d',' -f1 example_data.txt
# Kai     Refsnes 30
# Robin   Smith   25
# Sienna  Davis   40
```

### Select Specific Fields

The `-f` option allows you to select specific fields to display.

```bash
cut -f1-2 example_data.txt
# Kai     Refsnes
# Robin   Smith
# Sienna  Davis
```

### Show Complement

The `--complement` option allows you to show all fields except the selected ones.

```bash
cut --complement -f1 example_data.txt
# Refsnes 30,Norway
# Smith   25,Denmark
# Davis   40,Germany
```

### Advanced Field Extraction

```bash
cut -f2-3 example_data.txt
# Refsnes 30,Norway
# Smith   25,Denmark
# Davis   40,Germany
```

### Common Errors and Troubleshooting

## Bash `sort` Command - Sort Lines of Text Files

### Using the `sort` Command

The `sort` command is used to sort lines of text files.

It's a handy tool for organizing data in files.

### Basic Usage

```bash
sort fruits.txt
# apples,1
# bananas,2
# bananas,4
# kiwis,3
# kiwis,3
# oranges,20
```

### Options

- `-r` - Sort in reverse order
- `-n` - Sort numbers correctly
- `-k` - Sort by a specific column
- `-u` - Remove duplicate lines
- `-t` - Specify a delimiter for fields

### Sort in Reverse Order

```bash
sort -r fruits.txt
# oranges,20
# kiwis,3
# kiwis,3
# bananas,4
# bananas,2
# apples,1
```

### Specify a Delimiter for Fields

```bash
sort -t "," -k2,2 fruits.txt
# apples,1
# bananas,2
# oranges,20
# kiwis,3
# kiwis,3
# bananas,4
```

### Sort by a Specific Column

```bash
sort -t "," -k2,2 fruits.txt
# apples,1
# bananas,2
# oranges,20
# kiwis,3
# kiwis,3
# bananas,4
```

### Sort Numbers Correctly

The `-n` option allows you to sort numbers correctly.

Without this option, numbers are sorted lexicographically, meaning "10" would come before "2".

```bash
sort -t "," -n -k2,2 fruits.txt
# apples,1
# bananas,2
# kiwis,3
# kiwis,3
# bananas,4
# oranges,20
```

### Remove Duplicate Lines

```bash
sort -u fruits.txt
# apples,1
# bananas,2
# kiwis,3
# oranges,20
```

### Complex Sorting

```bash
sort -t "," -k1,1 -k2,2r fruits.txt
# apples,1
# bananas,4
# bananas,2
# kiwis,3
# kiwis,3
# oranges,20
```

## Bash `tail` Command - Display Last Part of Files

### Using the `tail` Command

The `tail` command is used to display the last part of files.

It's particularly useful for viewing the end of log files or any file that is being updated in real-time.

### Syntax

```bash
tail [OPTION]... [FILE]...
```

```bash
tail logfile.txt
# line 91
# line 92
# line 93
# line 94
# line 95
# line 96
# line 97
# line 98
# line 99
# line 100
```

### Options

- `-n [number]`: Display the last [number] lines of the file.
- `-f`: Follow the file as it grows, useful for monitoring log files.
- `-c [number]`: Display the last [number] bytes of the file.
- `--pid=[pid]`: Terminate after the process with the given PID dies.
- `--retry`: Keep trying to open a file even if it is inaccessible.

### Option: -n [number]

By default, `tail` shows the last 10 lines.

```bash
tail -n 5 logfile.txt
# line 96
# line 97
# line 98
# line 99
# line 100
```

### Option: -f

```bash
tail -f logfile.txt
# line 91
# line 92
# line 93
# line 94
# line 95
# line 96
# line 97
# line 98
# line 99
# line 100
# line 101
```

### Option: -c [number]

```bash
tail -c 20 logfile.txt

# end of logfile.txt
```

### Option: --pid=[pid]

```bash
tail -f --pid=1234 logfile.txt
# line 91
# line 92
# line 93
# ...
```

### Option: --retry

```bash
tail --retry -f logfile.txt
# tail: cannot open 'logfile.txt' for reading: No such file or directory
# line 91
# line 92
# line 93
# ...
```

### Use Cases

- Monitoring server logs to detect issues in real-time.
- Checking the latest entries in a continuously updated file.
- Debugging applications by reviewing recent log entries.

## Bash `head` Command - Display the beginning of a file

### Using the `head` Command

The `head` command is used to display the first part of files.

It's particularly useful for previewing the start of a file to understand its structure.

All examples below use the `logfile.txt` file:

```
line 01
line 02
line 03
line 04
line 05
line 06
line 07
line 08
line 09
line 10
...
```

### Basic Usage

```bash
head logfile.txt
# line 01
# line 02
# line 03
# line 04
# line 05
# line 06
# line 07
# line 08
# line 09
# line 10
```

### Options

- `-n [number]`: Display the first [number] lines of the file.
- `-c [number]`: Display the first [number] bytes of the file.

### Option: -n [number]

```bash
head -n 5 logfile.txt
# line 01
# line 02
# line 03
# line 04
# line 05
```

### Option: -c [number]

```bash
head -c 20 logfile.txt
# line 01
# line 02
# line 
``` 

### Option: Multiple Files

```bash
head -n 3 logfile.txt logfile2.txt
# ==> logfile.txt <==
# line 01
# line 02
# line 03

# ==> logfile2.txt <==
# line 01
# line 02
# line 03
``` 

### Option: -q

The `-q` option suppresses the printing of headers when multiple files are being processed.

```bash
head -q -n 3 logfile.txt logfile2.txt
# line 01
# line 02
# line 03
# line 01
# line 02
# line 03
```

### Common Uses

- Preview the start of a file to understand its structure.
- Quickly check the contents of a file without opening it fully.
- Extract the header information from a data file.