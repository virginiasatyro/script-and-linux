# Bash Tutorial - Networking

## Bash `ping` Command - Send Request to Network Hosts

### Using the `ping` Command

The `ping` command is used to send **ICMP ECHO_REQUEST** to network hosts.

It's a useful tool for checking network connectivity and diagnosing network issues.

### Basic Usage

```bash
ping google.com

Pinging google.com [142.250.74.110] with 32 bytes of data:
Reply from 142.250.74.110: bytes=32 time=79ms TTL=57
Reply from 142.250.74.110: bytes=32 time=52ms TTL=57
Reply from 142.250.74.110: bytes=32 time=48ms TTL=57
Reply from 142.250.74.110: bytes=32 time=38ms TTL=57

Ping statistics for 142.250.74.110:
    Packets: Sent = 4, Received = 4, Lost = 0 (0% loss),
Approximate round trip times in milli-seconds:
    Minimum = 38ms, Maximum = 79ms, Average = 54ms
```

### Options

- `-c` - Send a specific number of ping requests
- `-i` - Wait a specific number of seconds between sending each packet
- `-t` - Set the IP Time to Live (TTL)
- `-q` - Quiet output, only show summary
- `-s` - Specify the number of data bytes to be sent

### Send a Specific Number of Ping Requests

### Understanding Ping Results

- **Bytes**: The size of the ICMP packet sent
- **Time**: The round-trip time it took for the packet to reach the host and return, measured in milliseconds
- **TTL (Time to Live)**: The remaining lifespan of the packet, which decreases by one for each hop
- **Packet Loss**: The percentage of packets that were lost during transmission
- **Round-Trip Time Statistics**: Includes minimum, average, maximum, and standard deviation of the round-trip times

### Wait a Specific Number of Seconds Between Sending Each Packet

### Set the IP Time to Live (TTL)

### Quiet Output

### Specify Data Bytes

## Bash `curl` Command - Transfer a URL

### Using the `curl` Command

The `curl` command is used to transfer data from or to a server using various protocols like HTTP, HTTPS, FTP, and more.

It's a versatile tool for downloading files, testing APIs, and more.

### Basic Usage

```bash
curl http://example.com/file.txt
Hello, this is a test file.
There are three lines here.
This is the last line.
```

```bash
vivi_@virginia-PC MINGW64 /C/Users/vivi_/github/cpp-games/2048
$ curl https://example.com/file.txt
<!doctype html><html lang="en"><head><title>Example Domain</title><meta name="viewport" content="width=device-width, initial-scale=1"><style>body{background:#eee;width:60vw;margin:15vh auto;font-family:system-ui,sans-serif}h1{font-size:1.5em}div{opacity:0.8}a:link,a:visited{color:#348}</style></head><body><div><h1>Example Domain</h1><p>This domain is for use in documentation examples without needing permission. Avoid use in operations.</p><p><a href="https://iana.org/domains/example">Learn more</a></p></div></body></html>
```

### Options

- `-O` - Save the file with the same name as the remote file
- `-L` - Follow redirects
- `-I` - Fetch the HTTP headers only
- `-d` - Send data with POST request
- `-u` - Specify user and password for server authentication

### Save the File with the Same Name as the Remote File

### Follow Redirects

### Fetch the HTTP Headers Only

### Send Data with POST Request

### Specify User and Password for Server Authentication

### Understanding `curl` Output

- **HTTP Status Code**: Indicates the success or failure of the request.
- **Response Headers**: Provide metadata about the server response.
- **Response Body**: The actual content retrieved from the server.
- **Progress Meter**: Shows download progress and speed.

## Bash `wget` Command - Non-Interactive Network Downloader

### Using the `wget` Command

The `wget` command is used to download files from the web.

It's a powerful tool for downloading single files, entire websites, or even batch downloads.

### Basic Usage

```bash
wget http://example.com/file.txt
```

### Options

- `-b` - Run in the background
- `-q` - Quiet mode (no output)
- `-r` - Download directories recursively
- `-c` - Continue getting a partially-downloaded file
- `--limit-rate` - Limit download speed

### Run in the Background

### Quiet Mode

### Recursively Download

### Continue Getting a Partially-Downloaded File

### Limit Download Speed

### Understanding `wget` Output

- **Download Progress**: Shows the progress of the download.
- **File Size**: The size of the file being downloaded.
- **Download Speed**: The speed at which the file is being downloaded.
- **Time Remaining**: Estimated time remaining for the download to complete.

### Batch Downloads

## Bash `ssh` Command - OpenSSH SSH Client

### Using the ssh Command

The `ssh` command is used to connect to a remote machine securely.

### Basic Usage

```bash
ssh user@example.com
Linux raspberrypi 6.6.74+rpt-rpi-2712 #1 SMP PREEMPT Debian 1:6.6.74-1+rpt1 (2025-01-27) aarch64

The programs included with the Debian GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
Last login: Thu Apr 10 13:09:32 2025 from 45.14.193.140
user@example.com:~ $
```

### SSH Options

- `-p` - Specify the port
- `-i` - Use a private key file
- `-v` - Enable verbose mode
- `-C` - Enable compression
- `-X` - Enable X11 forwarding
- `-o` - Specify options directly on the command line

### Option: -p (Port)

### Option: -i (Identity File)

### Option: -v (Verbose Mode)

### Option: -C (Compression)

### Option: -X (X11 Forwarding)

### Option: -o (Specify Options)

### Troubleshooting Common Issues

- **Connection Refused**: Ensure the SSH service is running on the remote server and the correct port is being used. Check firewall settings to make sure they are not blocking the connection.
- **Host Key Verification Failed**: This happens when the server's host key changes. Verify the server's identity and update the known_hosts file by removing the old key entry.
- **Permission Denied**: Check permissions and username. Check the server's SSH configuration for restrictions.
- **Timeouts**: Check network connectivity and server responsiveness. Adjust the SSH timeout settings if necessary.

## Bash `scp` Command - Secure Copy

### Using the `scp` Command

The `scp` command is used to securely copy files between hosts on a network.

### Basic Usage

```bash
scp file.txt user@example.com:/home/user/
user@example.com's password: 
file.txt
```

### Options

- `-r` - Recursively copy entire directories
- `-P` - Specify the port to connect to on the remote host
- `-i` - Specify an identity (private key) file
- `-C` - Enable compression
- `-v` - Enable verbose mode
- `-l` - Limit the bandwidth used by the copy

### Option: `-r` (Recursive Copy)

### Option: `-P` (Port)

### Option: `-i` (Identity File)

### Option: `-C` (Compression)

### Option: `-v` (Verbose Mode)

### Option: `-l` (Limit Bandwidth)

### Understanding `scp` Output

- **Transfer Progress**: Shows progress of the file transfer.
- **File Size**: The size of the file being transferred.
- **Transfer Speed**: The speed at which the file is being transferred.
- **Time Remaining**: Estimated time remaining for the transfer to complete.

## Bash `rsync` Command - Remote (and local) File-copying

### Using the `rsync` Command

The `rsync` command is used to efficiently transfer and synchronize files across computer systems, by checking the timestamp and size of files.

### Basic Usage

```bash
rsync -avz /local/dir/ user@example.com:/remote/dir/
```

### Understanding Rsync Output

- **File List**: Lists the files being transferred.
- **Transfer Progress**: Shows the progress of each file transfer.
- **Compression Ratio**: Indicates the effectiveness of compression if used.
- **Speed**: The speed at which files are being transferred.

### Rsync Options Overview

- `-a` - Archive mode
- `-v` - Increase verbosity
- `-z` - Compress file data
- `--delete` - Delete extraneous files
- `-r` - Recurse into directories
- `-u` - Skip files that are newer on the receiver
- `--progress` - Show progress during transfer

### Option: `-a` (Archive Mode)

### Option: `-v` (Verbose Mode)

### Option: `-z` (Compression)

### Option: `--delete`

### Option: `-r` (Recursive)

### Option: `-u` (Update)

### Option: `--progress`

### Troubleshooting Common Issues