# Bash Tutorial

## Bash HOME

Bash is used to write scripts and run commands on Linux systems.

It helps automate tasks, manage system operations, and boost productivity.

### Understanding Shells

A shell is a text-based interface that lets you talk to your computer.

There are different types of shells, but Bash (Bourne Again SHell) is the most popular because it's powerful and easy to use.

**Types of Shells**:

- **Bourne Shell (sh)**: The original Unix shell, developed by Stephen Bourne.
- **C Shell (csh)**: Known for its C-like syntax, popular for interactive use.
- **Korn Shell (ksh)**: Combines features of sh and csh, offering advanced scripting capabilities.
- **Bash (Bourne Again SHell)**: An improved version of sh, with additional features like command history and tab completion.

Why Use Bash?

- It is widely available on Unix/Linux systems, making scripts portable.
- Supports powerful scripting features, including loops, conditionals, and functions.
- Provides command history and tab completion for ease of use.
- Can be integrated with other Unix/Linux tools for automation.

### Learning by Examples

```bash
virginia@virginia-PC:~$ bash --version
GNU bash, version 5.0.17(1)-release (x86_64-pc-linux-gnu)
Copyright (C) 2019 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>

This is free software; you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
```

## Bash Introduction

### What is Bash?

Bash is used to run commands and write scripts on Unix/Linux systems.

Bash is the default shell on most Linux and macOS systems.

### Why Learn Bash?

Bash is a powerful tool for developers and system administrators.

Understanding and mastering Bash is important for working in Unix/Linux.

### Shell vs. Bash Shell

A "Shell" is any command-line tool. "Bash shell" is specifically the Bourne Again SHell.

Because of the popularity, Bash is often what people think of when they say shell

This tutorial will teach you how to use Bash.

### Practical Uses of Bash
System administrators use Bash to:

- Automate tasks
- System operations
- Process data

Developers use Bash for:

- Build automation
- Testing
- Deployment
- Data processing and manipulation

## Getting Started with Bash

### Setting Up Bash

```bash
bash --version

sudo apt-get install bash
```

### Running Bash Commands

You can also write scripts (a list of commands) in a file with a `.sh` extension:

```bash
#!/bin/bash
echo "Hello, Bash!"
```