# Bash Tutorial - Basic Commands

## Bash Commands Overview

### Common Bash Commands

Bash commands are how you interact with the operating system and perform tasks.

Common commands:

- `ls` - List directory contents
- `cd` - Change the current directory
- `pwd` - Print the current working directory
- `echo` - Display a line of text
- `cat` - Concatenate and display files
- `cp` - Copy files and directories
- `mv` - Move or rename files
- `rm` - Delete files or folders
- `touch` - Create an empty file or update its time
- `mkdir` - Create a new folder

```bash
mkdir my_directory
cd my_directory
touch my_file.txt
ls
my_file.txt
```

## Bash `ls` Command - List Directory Contents

### Using the ls Command

The `ls` command is used to list the contents of a directory.

The `ls` command can display files, directories, and information about them.

### Basic Usage

To see what's in the current folder, use ls:

```bash
ls
Cosmere_RPG_Beta_Rules_Preview.pdf  images/
my_file.txt  report.csv  voiceover.wav
```

### Options Overview

The ls command has a variety of options to customize its output:

- `-l` - Long listing format
- `-a` - Include hidden files
- `-h` - Human-readable sizes
- `-t` - Sort by modification time
- `-r` - Reverse order while sorting
- `-R` - List subdirectories recursively
- `-S` - Sort by file size
- `-1` - List one file per line
- `-d` - List directories themselves, not their contents
- `-F` - Append indicator (one of */=@|) to entries

### Long Listing Format

The `-l` option gives you detailed information about files and folders.

It displays information such as:

- file permissions
- number of links
- owner name
- owner group
- file size
- time of last modification
- file or directory name

```bash
ls -l
total 24232
-rw-r--r-- 1 user 197609 23777028 Jan 15 20:38 Cosmere_RPG_Beta_Rules_Preview.pdf
drwxr-xr-x 1 user 197609        0 Apr  9 07:46 images/
-rw-r--r-- 1 user 197609      890 Apr  9 07:48 my_file.txt
-rw-r--r-- 1 user 197609   305366 Apr  9 07:48 report.csv
-rw-r--r-- 1 user 197609   720974 Apr  9 07:47 voiceover.wav
```

The `-a` option includes hidden files in the listing.

```bash
ls -a
./  ../  .my_secret_file  Cosmere_RPG_Beta_Rules_Preview.pdf
images/  my_file.txt  report.csv  voiceover.wav
```

### Human-Readable Sizes

The `-h` option makes file sizes easier to read by converting byte counts into kilobytes (K), megabytes (M), gigabytes (G), etc.

```bash
ls -lh
total 24M
-rw-r--r-- 1 user 197609  23M Jan 15 20:38 Cosmere_RPG_Beta_Rules_Preview.pdf
drwxr-xr-x 1 user 197609    0 Apr  9 07:51 images/
-rw-r--r-- 1 user 197609  890 Apr  9 07:48 my_file.txt
-rw-r--r-- 1 user 197609 299K Apr  9 07:48 report.csv
-rw-r--r-- 1 user 197609 705K Apr  9 07:47 voiceover.wav
```

### Sorting by Time

The -t option sorts files and directories by modification time, with the most recently modified files first.

This option is useful when you want to see the most recently updated files first.

```bash
ls -t
images/  my_file.txt  report.csv  voiceover.wav
Cosmere_RPG_Beta_Rules_Preview.pdf
```

### Reverse Order

The `-r` option reverses the order of the sort.

When used in combination with other options like `-t`, it can display the oldest files first.

```bash
ls -r
voiceover.wav  report.csv  my_file.txt  images/
Cosmere_RPG_Beta_Rules_Preview.pdf
```

### Recursive Listing

The `-R` option lists directories and their contents recursively.

This is useful for viewing the entire directory tree.

```bash
ls -R
.:
copy_of_my_file.txt  Cosmere_RPG_Beta_Rules_Preview.pdf
images/  my_file.txt  myfolder/  report.csv  voiceover.wav

./images:
1.png  2.png  3.png  4.png

./myfolder:
my_file.txt  new_directory/

./myfolder/new_directory:
```

### Sort by Size

The `-S` option sorts files by size, with the largest files first.

```bash
ls -S
Cosmere_RPG_Beta_Rules_Preview.pdf  voiceover.wav  report.csv
copy_of_my_file.txt  my_file.txt  images/  myfolder/
```

### One File per Line

The `-1` option lists one file per line, which is useful for scripts or when piping output to other commands.

```bash
ls -1
Cosmere_RPG_Beta_Rules_Preview.pdf
images/
my_file.txt
report.csv
voiceover.wav
```

### Directories Only

The `-d` option lists directories themselves rather than their contents.

```bash
ls -d */
images//  myfolder//
```

### Append Indicator

The `-F` option appends an indicator character to entries (e.g., / for directories, * for executables).

```bash
ls -F
Cosmere_RPG_Beta_Rules_Preview.pdf  images/
my_file.txt  report.csv  voiceover.wav
```

### Using Multiple Options

```bash
ls -l -a
total 24248
drwxr-xr-x 1 user 197609        0 Apr  9 07:53 ./
drwxr-xr-x 1 user 197609        0 Apr  9 07:42 ../
-rw-r--r-- 1 user 197609      890 Apr  9 07:48 .my_secret_file
-rw-r--r-- 1 user 197609 23777028 Jan 15 20:38 Cosmere_RPG_Beta_Rules_Preview.pdf
drwxr-xr-x 1 user 197609        0 Apr  9 07:51 images/
-rw-r--r-- 1 user 197609      890 Apr  9 07:48 my_file.txt
-rw-r--r-- 1 user 197609   305366 Apr  9 07:48 report.csv
-rw-r--r-- 1 user 197609   720974 Apr  9 07:47 voiceover.wav
```

```bash
ls -la
total 24248
drwxr-xr-x 1 user 197609        0 Apr  9 07:53 ./
drwxr-xr-x 1 user 197609        0 Apr  9 07:42 ../
-rw-r--r-- 1 user 197609      890 Apr  9 07:48 .my_secret_file
-rw-r--r-- 1 user 197609 23777028 Jan 15 20:38 Cosmere_RPG_Beta_Rules_Preview.pdf
drwxr-xr-x 1 user 197609        0 Apr  9 07:51 images/
-rw-r--r-- 1 user 197609      890 Apr  9 07:48 my_file.txt
-rw-r--r-- 1 user 197609   305366 Apr  9 07:48 report.csv
-rw-r--r-- 1 user 197609   720974 Apr  9 07:47 voiceover.wav
```

## Bash `cd` - Change Directory

### Basic Usage

```bash
cd my_directory
```

### Options Overview

The `cd` command supports several useful options for navigating directories:

- `cd ..`: Move up one directory level
- `cd ~`: Change to the home directory
- `cd -`: Switch to the previous directory
- `cd /`: Change to the root directory

### Combining Options

```bash
cd my_directory && ls
copy_of_my_file.txt  Cosmere_RPG_Beta_Rules_Preview.pdf
images/  my_file.txt  myfolder/  report.csv  voiceover.wav
```

## Bash `pwd` Command - Print Working Directory

```bash
pwd
/home/user/my_directory
```

### Options Overview

The `pwd` command supports a few options to customize its output:

`-L`: Display the logical current working directory
`-P`: Display the physical current working directory (without symbolic links)

```bash
pwd -L
/home/user/my_directory
pwd -P
```

## Bash `echo` Command - Display Text

### Basic Usage

```bash
echo "Hello, World!"
Hello, World!
```

### Options Overview

The `echo` command has several options to customize its output:

- `-n` - Don't add a new line at the end
- `-e` - Allow special characters like \n for new lines
- `-E` - Don't allow special characters (default)

```bash
echo -n "Hello,";echo " World!"
Hello, World!

echo -e "Hello\nWorld!"
Hello
World!

echo -E "Hello\nWorld!"
Hello\nWorld!
```

### Using `echo` in Scripts

The `echo` command is often used in scripts for debugging or logging information. It helps you see what's happening in your script by printing messages to the terminal.

```bash
#!/bin/bash
echo "Starting the script..."
# Your script commands here
echo "Script finished."
```

## Bash `cat` Command - Concatenate and Display Files

The `cat` command is used to show the content of files in the terminal.

### Basic Usage

```bash
cat my_file.txt
Understanding Shells
A shell is a text-based interface that lets you talk to your computer.

There are different types of shells. Bash (Bourne Again SHell)
is popular because it's powerful and easy to use.
```

### Options

The `cat` command has options to change how it shows text:

- `-n` - Add numbers to each line
- `-b` - Add numbers only to lines with text
- `-s` - Remove extra empty lines
- `-v` - Show non-printing characters (except for tabs and end of line)

```bash
cat -n my_file.txt
    1  Understanding Shells
    2  A shell is a text-based interface that lets you talk to your computer.
    3
    4  There are different types of shells. Bash (Bourne Again SHell)
    5  is popular because it's powerful and easy to use.
```

```bash
cat -b my_file.txt
    1  Understanding Shells
    2  A shell is a text-based interface that lets you talk to your computer.

    3  There are different types of shells. Bash (Bourne Again SHell)
    4  is popular because it's powerful and easy to use.
```

```bash
cat -s my_file.txt
Understanding Shells
A shell is a text-based interface that lets you talk to your computer.
There are different types of shells. Bash (Bourne Again SHell)
is popular because it's powerful and easy to use.
```

### Concatenate Two Files

The `cat` command can be used to concatenate multiple files into one.

```bash
cat file1.txt file2.txt > combined.txt
```

### Using `cat` with Piping

The `cat` command is often used with piping to send the content of files to other commands.

```bash
cat my_file.txt | grep "shells"
Understanding Shells
There are different types of shells. Bash (Bourne Again SHell)
```

## Bash `cp` - Copy Files and Directories

### Basic Usage

```bash
# cp source_file destination_file:
cp my_file.txt copy_of_my_file.txt
```

### Options

The `cp` command has options to change how it works:

- `-r` - Copy all files and folders inside a directory
- `-i` - Ask before replacing files
- `-u` - Copy only if the source is newer
- `-v` - Verbose mode, show files being copied

```bash
cp -v my_file.txt copy_of_my_file.txt
'my_file.txt' -> 'copy_of_my_file.txt'
```

```bash
# copy entire directories
cp -r images images2
```

```bash
# The -i option will prompt you before overwriting file
cp -i my_file.txt copy_of_my_file.txt
cp: overwrite copy_of_my_file.txt?
```

```bash
# The -u option copies files only if the source file is newer than the destination file.
cp -u new_file.txt existing_file.txt
```

### Using `cp` with Wildcards

Wildcards allow you to copy multiple files at once. For example, `cp *.txt /destination/` will copy all text files to the destination folder.

```bash
cp *.txt /destination/
```

## Bash `mv` Command - Move or Rename Files

The `mv` command is used to move or rename files and directories.

### Basic Usage

To move a file, use `mv source_file destination_directory`:

```bash
mv my_file.txt /path/to/destination/
```

### Renaming Files

To rename a file, use `mv old_name new_name`:

```bash
mv old_name.txt new_name.txt
```

### Options Overview

The `mv` command has several options to customize its behavior:

- `-i` - Ask before replacing files
- `-u` - Move only if the source is newer
- `-v` - Verbose mode, show files being moved

```bash
# The -i option will prompt you before overwriting files
mv -i my_file.txt myfolder/
mv: overwrite 'myfolder/my_file.txt'?
```

```bash
# The -u option moves files only if the source file is newer than the destination file.
mv -u new_file.txt /path/to/destination/
```

```bash
# The -v option enables verbose mode, which displays the files being moved in the terminal.
mv -v my_file.txt myfolder/new_directory/  
renamed 'my_file.txt' -> 'myfolder/new_directory/my_file.txt'
```

```bash
#  Using Wildcards
mv *.txt /destination/
```

## Bash `rm` Command - Remove Files or Directories

The `rm` command is used to remove files or directories. Be careful, as removed files cannot be easily recovered.

### Basic Usage

To remove a file, use `rm` filename:

```bash
rm my_file.txt
```

### Options

The `rm` command has options to change how it works:

- `-r` - Delete a folder and everything inside it
- `-i` - Ask before deleting each file
- `-f` - Force delete without asking
- `-v` - Verbose mode, show files being removed

```bash
# The -v option enables verbose mode,
rm -v my_new_file.txt
removed 'my_new_file.txt'
```

```bash
# The -r option allows you to delete directories and all their contents.
rm -r directory
```

```bash
# The -i option will prompt you before each file is deleted
rm -i my_file.txt
rm: remove regular file 'my_file.txt'?
```

```bash
# The -f option forces deletion without any prompts.
rm -f file.txt
```

```bash
# Always double-check the files and directories you are about to delete, especially when using the -r and -f options.
rm -i -r images
rm: descend into directory 'images'?
```

## Bash touch Command - Change File Timestamps

The touch command is used to change file timestamps or create an empty file if it doesn't exist.

### Basic Usage

```bash
# To update the access and modification times of a file, use touch filename:
touch file.txt
```

### Options

The touch command has options to change how it works:

- `-a` - Update only when the file was last read
- `-m` - Update only when the file was last changed
- `-t` - Set the timestamp to a specific time
- `-c` - Do not create any files

```bash
# The -a option lets you update the access time of a file.
touch -a file.txt
```

```bash
# The -m option lets you update only the modification time of a file.
ls -l
-rw-r--r-- 1 user 197609 208 Apr  9 06:24 my_file.txt
touch -m my_file.txt
ls -l
-rw-r--r-- 1 user 197609 208 Apr  9 08:25 my_file.txt
```

```bash
# The -t option allows you to set the timestamp to a specific time.
ls -l
-rw-r--r-- 1 user 197609 208 Apr  9 06:24 my_file.txt
touch -t 202501010000 my_file.txt
ls -l
-rw-r--r-- 1 user 197609 208 Jan  1 00:00 my_file.txt
```

```bash
# The -c option tells touch not to create any files if they do not exist.
touch -c non_existent_file.txt
```

```bash
# Wildcards allow you to update timestamps on multiple files at once.
# Update the timestamps of all text files in the directory.
touch *.txt
```

## Bash `mkdir` Command - Make Directories

The `mkdir` command is used to create new directories.

```bash
# To create a new directory, use mkdir directory_name:
mkdir new_directory
```

### Options Overview

The `mkdir` command has several options to customize its behavior:

- `-p` - Create parent directories as needed
- `-v` - Show a message for each created directory
- `-m` - Set file mode (permissions)

```bash
# Create Parent Directories
mkdir -p parent/child
```

```bash
# The -v option prints a message for each directory created, which is helpful for tracking what happens.
mkdir -v new_directory
mkdir: created directory 'new_directory'
```

```bash
# The -m option allows you to set the file mode (permissions) for the new directories.
mkdir -m 755 new_directory
```

## Bash `man` Command - User Manual

The `man` command is used to display the user manual of any command that can be run on the terminal.

The basic syntax of the `man` command is:

```bash
# Man Command Syntax
man [command]
```

### Common Uses

The `man` command is commonly used to:

- Learn about command options and usage.
- Understand command syntax and examples.
- Access detailed documentation for troubleshooting.

## Bash alias

Aliases in Bash allow you to create shortcuts for long or frequently used commands. This makes it easier to execute complex commands with a simple keyword.

### Creating Aliases

To create an alias, use the syntax `alias name='command'`, where name is the shortcut you want to use, and command is the full command you want to run.

```bash
# Simple Alias - List
alias ll='ls -la'
```

```bash
# Simple Alias - Git Status
alias gs='git status'
```

```bash
# Viewing Aliases
alias
alias ll='ls -l'
alias gs='git status'
```

```bash
# Removing an Alias
unalias gs
```

### Creating Permanent Aliases

To make an alias permanent, add it to your `~/.bashrc` or `~/.bash_profile` file.

```bash
# Adding Permanent Alias - Add Alias
alias ll='ls -la'
```

```bash
# Adding Permanent Alias - Save and Apply
source ~/.bashrc
```