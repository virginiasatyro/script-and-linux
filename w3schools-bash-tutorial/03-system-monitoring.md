# Bash Tutorial - System Monitoring

## Bash `ps` Command - Snapshot of Current Processes

### Using the `ps` Command

The `ps` command is used to report a snapshot of current processes.

It's a useful tool for monitoring and managing processes on your system.

All examples below use a hypothetical process list for demonstration:

```
PID TTY          TIME CMD
1234 pts/0    00:00:01 bash
5678 pts/1    00:00:02 python
9101 pts/2    00:00:03 node
```

### Understanding the Output

- **PID**: Process ID, a unique identifier for each process.
- **TTY**: Terminal type associated with the process.
- **TIME**: Total CPU time used by the process.
- **CMD**: The command that started the process.

### Basic Usage

```bash
ps
# PID TTY          TIME CMD
# 1234 pts/0    00:00:01 bash
# 5678 pts/1    00:00:02 python
# 9101 pts/2    00:00:03 node
``` 

### Options

- `-e` - Show all processes
- `-f` - Show detailed information
- `-u` - Show processes for a specific user
- `-a` - Show all processes with a terminal
- `-x` - Show processes without a terminal

### Show All Processes

### Show Detailed Information

### Show Processes for a Specific User

### Show Processes with a Terminal

### Show Processes without a Terminal

### Combining Options

## Bash `top` Command - Display Linux Tasks

### Using the `top` Command

The `top` command is used to display Linux tasks.

It's a powerful tool for monitoring system performance in real-time.

All examples below use a hypothetical output for demonstration:

```
top - 08:00:01 up 10 days,  3:22,  3 users,  load average: 0.01, 0.05, 0.10
Tasks: 123 total,   1 running, 122 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.7 us,  0.3 sy,  0.0 ni, 98.7 id,  0.3 wa,  0.0 hi,  0.0 si,  0.0 st
KiB Mem :  8163100 total,  123456 free,  234567 used,  345678 buff/cache
KiB Swap:  2097148 total,  1048576 free,  1048572 used.  456789 avail Mem

  PID USER      PR  NI    VIRT    RES    SHR S  %CPU %MEM     TIME+ COMMAND
 1234 user      20   0  123456  12345   1234 S   0.3  0.2   0:01.23 bash
 5678 user      20   0  234567  23456   2345 S   0.5  0.3   0:02.34 python
 9101 user      20   0  345678  34567   3456 S   0.7  0.4   0:03.45 node
```

### Understanding the Output

- **PID**: Process ID, a unique identifier for each process.
- **USER**: The user account that owns the process.
- **PR**: Priority of the process.
- **NI**: Nice value, which affects scheduling priority.
- **VIRT**: Virtual memory size used by the process.
- **RES**: Resident memory size, the non-swapped physical memory the process uses.
- **SHR**: Shared memory size.
- **S**: Process status (e.g., S for sleeping, R for running).
- **%CPU**: CPU usage percentage.
- **%MEM**: Memory usage percentage.
- **TIME+**: Total CPU time the process has used since it started.
- **COMMAND**: The command that started the process.

### Basic Usage

### Options

- `-d` - Set the time between updates
- `-p` - Monitor specific PIDs
- `-u` - Show tasks for a specific user
- `-n` - Set the number of iterations
- `-b` - Batch mode operation

### Set Update Interval

### Monitor Specific PIDs

### Show Tasks for a Specific User

### Set Number of Iterations

### Batch Mode Operation

### Combining Options

## Bash `df` Command - File System Disk Space Usage

### Using the `df` Command

The `df` command is used to report file system disk space usage.

It's a useful tool for checking available storage on your system.

```
Filesystem     1K-blocks    Used Available Use% Mounted on
/dev/sda1       20480000 1024000  19456000   5% /
tmpfs            4096000       0   4096000   0% /dev/shm
/dev/sdb1       10240000  512000   9728000   5% /mnt/data
```

### Understanding the Output

- **Filesystem**: The name of the file system.
- **1K-blocks**: Total size of the file system in 1K blocks.
- **Used**: Amount of space used.
- **Available**: Amount of space available for use.
- **Use%**: Percentage of space used.
- **Mounted on**: Directory where the file system is mounted.

### Basic Usage

### Options

- `-h` - Show sizes in human-readable format (e.g., KB, MB)
- `-a` - Show all file systems, even empty ones
- `-T` - Show the type of file system
- `-i` - Show inode usage
- `-P` - Use POSIX output format

### Show Sizes in Human-Readable Format

### Show All File Systems

### Show File System Type

### Show Inode Usage

### Use POSIX Output Format

### Combining Options

## Bash `du` Command - File Space Usage

The `du` command is used to estimate file space usage.

It's helpful for finding out how much space files and directories take up.

### Understanding the Output

- **Size**: The amount of disk space used by the file or directory.
- **Path**: The file or directory path.

### Basic Usage

### Options

- `-h` - Show sizes in human-readable format (e.g., KB, MB)
- `-s` - Show only the total size for each item
- `-a` - Show sizes for all files, not just directories
- `-c` - Produce a grand total
- `--max-depth=N` - Limit the depth of directory traversal

### Show Sizes in Human-Readable Format

### Show Only Total Size

### Show Sizes for All Files

### Produce a Grand Total

### Limit Directory Traversal Depth

### Combining Options

## Bash `free` Command - Display Free and Used Memory

### Using the `free`  Command

The `free` command is used to display the amount of free and used memory in the system.

It's useful for monitoring memory usage and managing system resources.

### Basic Usage

```bash
free -k
#               total        used        free      shared  buff/cache   available
# Mem:        8176588     1376568     5869188      146532     1051172     6352280
# Swap:       2097148           0     2097148
```

### Options

- `-h` - Show memory in human-readable format (e.g., KB, MB, GB)
- `-b` - Show memory in bytes
- `-k` - Show memory in kilobytes (KB)
- `-m` - Show memory in megabytes (MB)
- `-g` - Show memory in gigabytes (GB)
- `-s [interval]` - Continuously display memory usage at specified intervals
- `-t` - Display total memory

### Show Memory in Human-Readable Format

### Show Memory in Bytes

### Show Memory in Kilobytes

### Show Memory in Megabytes

### Show Memory in Gigabytes

### Continuously Display Memory Usage

### Display Total Memory

## Bash `kill` Command - Terminate Processes

### Using the `kill` Command

The `kill` command is used to terminate processes in a Unix-like operating system.

It's a powerful tool for managing system resources and ensuring that processes do not consume more resources than necessary.

### Common Uses

- Terminate unresponsive processes.
- Manage system resources by stopping unnecessary processes.
- Send specific signals to processes for custom handling.

### Syntax

### Options

- `-9`: Forcefully terminate a process.
- `-l`: List all signal names.
- `-s [signal]`: Specify a signal to send.
- `-p`: Print the process ID.

### Forcefully Terminate a Process

```bash
kill -9 [PID]
```

### List All Signal Names

### Specify a Signal to Send

### Print the Process ID

## Bash `uptime` Command - System Runtime

### Using the `uptime` Command

The `uptime` command is used to find out how long the system has been running.

It provides a quick overview of the system's performance, including:

- The current time
- How long the system has been up
- The number of users logged in
- The system load averages for the past 1, 5, and 15 minutes

### Syntax

```bash
uptime
```

### Understanding the Output

- **Current Time**: The time at which the command was run.
- **Uptime Duration**: How long the system has been running since the last reboot.
- **Number of Users**: The number of users currently logged into the system.
- **Load Averages**: The system load averages for the past 1, 5, and 15 minutes.

### Example Output

```bash
uptime
# 14:36:01 up 10 days,  3:45,  4 users,  load average: 0.75, 0.60, 0.50
```

- The current time is 14:36:01.
- The system has been up for 10 days, 3 hours, and 45 minutes.
- There are 4 users currently logged in.
- The load averages are 0.75, 0.60, and 0.50, indicating the system load over the last 1, 5, and 15 minutes.

### Interpreting Load Averages

- A lower load average indicates a less busy system.
- A higher load average suggests the system is busier.
- Load averages above 1.0 per core may indicate the system is overloaded.

```bash
load average: 0.75, 0.60, 0.50
```

In this example, the system load is decreasing over time, indicating that the system is becoming less busy.

### Common Uses

- Monitor system performance and stability.
- Quickly check how long the system has been running.
- Assess system load and determine if the system is under heavy use.