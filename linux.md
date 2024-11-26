# Common Linux Commands

## Table of Contents
- [Common Linux Commands](#common-linux-commands)
  - [Table of Contents](#table-of-contents)
  - [File and Directory Management](#file-and-directory-management)
  - [File Viewing and Editing](#file-viewing-and-editing)
  - [System Information](#system-information)
  - [Process Management](#process-management)
  - [Network Management](#network-management)
  - [Permissions](#permissions)
  - [Package Management (RHEL-based)](#package-management-rhel-based)
  - [Searching](#searching)
  - [Environment Variables](#environment-variables)
  - [Firewall Management](#firewall-management)
  - [System Control (systemctl)](#system-control-systemctl)

## File and Directory Management
| Command | Description |
|---------|-------------|
| `ls`    | List directory contents <br> `-l` : Use a long listing format <br> `-a` : Include directory entries whose names begin with a dot (.) <br> `-h` : With -l, print sizes in human readable format (e.g., 1K 234M 2G) |
| `cd`    | Change directory |
| `pwd`   | Print working directory |
| `mkdir` | Create a new directory <br> `-p` : Create parent directories as needed |
| `rm`    | Remove files or directories <br> `-r` : Remove directories and their contents recursively <br> `-f` : Ignore nonexistent files and arguments, never prompt |
| `cp`    | Copy files or directories <br> `-r` : Copy directories recursively <br> `-i` : Prompt before overwrite |
| `mv`    | Move or rename files or directories <br> `-i` : Prompt before overwrite |
| `ln`    | Create hard and symbolic links <br> `-s` : Create symbolic links instead of hard links |
| `zip`   | Package and compress files <br> `-r` : Recursively zip directories <br> `-e` : Encrypt the zip file | `zip archive.zip file1 file2` (Create a zip archive) |
| `unzip` | Extract compressed files from a zip archive <br> `-l` : List the contents of a zip file <br> `-d` : Extract files into a specific directory | `unzip archive.zip` (Extract a zip archive) |
| `tar`   | Archive files <br> `-c` : Create a new archive <br> `-x` : Extract files from an archive <br> `-v` : Verbosely list files processed <br> `-f` : Specify the archive file name <br> `-z` : Compress the archive using gzip <br> `-j` : Compress the archive using bzip2 | `tar -cvf archive.tar file1 file2` (Create a tar archive) <br> `tar -xvf archive.tar` (Extract a tar archive) <br> `tar -czvf archive.tar.gz file1 file2` (Create a compressed tar.gz archive) <br> `tar -xzvf archive.tar.gz` (Extract a tar.gz archive) |
| `rpm2cpio` | Convert an RPM package to a cpio archive | `rpm2cpio package.rpm | cpio -idmv` (Extract files from an RPM package) |

## File Viewing and Editing
| Command | Description |
|---------|-------------|
| `cat`   | Concatenate and display file content <br> `-n` : Number all output lines |
| `less`  | View file content one page at a time <br> `-N` : Show line numbers <br> `/pattern` : Search for a pattern <br> `n` : Go to the next match <br> `p` : Go to the previous match <br> `g` : Go to the beginning of the file <br> `G` : Go to the end of the file <br> `q` : Quit |
| `vim`   | Advanced text editor <br> `i` : Insert mode <br> `Esc` : Exit insert mode <br> `:w` : Save file <br> `:q` : Quit <br> `:wq` : Save and quit <br> `:q!` : Quit without saving <br> `/pattern` : Search for a pattern <br> `n` : Go to the next match <br> `N` : Go to the previous match <br> `dd` : Delete a line <br> `yy` : Copy a line <br> `p` : Paste after the cursor <br> `u` : Undo <br> `Ctrl+r` : Redo |

## System Information
| Command   | Description |
|-----------|-------------|
| `uname -a`| Display all system information |
| `top`     | Display tasks and system status <br> `-u` : Display tasks for a specific user |
| `df`      | Report file system disk space usage <br> `-h` : Print sizes in human readable format (e.g., 1K 234M 2G) |
| `du`      | Estimate file space usage <br> `-h` : Print sizes in human readable format (e.g., 1K 234M 2G) <br> `-s` : Display only a total for each argument |
| `free`    | Display memory usage <br> `-h` : Print sizes in human readable format (e.g., 1K 234M 2G) |
| `lscpu`   | Display information about the CPU architecture |
| `cat /proc/cpuinfo` | Display detailed information about the CPU |
| `hostnamectl set-hostname new-hostname` | Change the system hostname |
| `echo "127.0.0.1 new-hostname" >> /etc/hosts` | Add a new hostname to the hosts file |
| `date` | Display or set the system date and time |
| `timedatectl` | Control the system time and date |
| `timedatectl set-timezone <timezone>` | Set the system timezone |

## Process Management
| Command  | Description |
|----------|-------------|
| `ps`     | Report a snapshot of current processes <br> `-e` : Select all processes <br> `-f` : Full format listing |
| `kill`   | Terminate a process by PID <br> `-9` : Forcefully terminate a process |
| `killall`| Terminate processes by name |
| `bg`     | Resume a suspended job in the background |
| `fg`     | Bring a job to the foreground |
| `strace` | Trace system calls and signals <br> `-p` : Attach to the process with the process ID |
| `pidof`  | Find the process ID of a running program |
| `lsof`   | List open files and the processes that opened them |
| `ls -l /proc/<pid>/fd` | List file descriptors for a specific process |

## Network Management
| Command   | Description |
|-----------|-------------|
| `ping`    | Send ICMP ECHO_REQUEST to network hosts <br> `-c` : Stop after sending (and receiving) count ECHO_REQUEST packets |
| `ifconfig`| Configure a network interface <br> `-a` : Display all interfaces which are currently available, even if down |
| `wget`    | Non-interactive network downloader <br> `-q` : Turn off Wget's output <br> `-O` : Write documents to FILE |
| `curl`    | Transfer data from or to a server <br> `-o` : Write output to FILE instead of stdout <br> `-I` : Fetch the HTTP-header only |
| `netstat` | Print network connections, routing tables, interface statistics, masquerade connections, and multicast memberships <br> `-t` : Display TCP connections <br> `-u` : Display UDP connections <br> `-l` : Display listening server sockets <br> `-p` : Show the PID and name of the program to which each socket belongs <br> `-r` : Display the kernel routing tables <br> `-n` : Show numerical addresses instead of resolving hosts <br> `-a` : Show all sockets (listening and non-listening) |

## Permissions
| Command  | Description |
|----------|-------------|
| `chmod`  | Change file modes or Access Control Lists <br> `-R` : Change files and directories recursively |
| `chown`  | Change file owner and group <br> `-R` : Operate on files and directories recursively |
| `sudo`   | Execute a command as another user <br> `-u` : Run the command as a user other than the default target user (root) |

## Package Management (RHEL-based)
| Command         | Description |
|-----------------|-------------|
| `yum update`    | Update package lists |
| `yum upgrade`   | Upgrade all packages |
| `yum install`   | Install a package |
| `yum remove`    | Remove a package |

## Searching
| Command | Description |
|---------|-------------|
| `grep`  | Print lines matching a pattern <br> `-r` : Read all files under each directory, recursively <br> `-i` : Ignore case distinctions |
| `find`  | Search for files in a directory hierarchy <br> `-name` : Base of file name (the path with the leading directories removed) matches shell pattern <br> `-type` : File is of type (e.g., `f` for regular file, `d` for directory) |

## Environment Variables
| Command | Description |
|---------|-------------|
| `export VAR=value` | Set a global environment variable |
| `VAR=value` | Set a local environment variable |
| `echo 'export VAR=value' >> ~/.bashrc` | Set a persistent environment variable |

## Firewall Management
| Command | Description | Example |
|---------|-------------|---------|
| `iptables -L` | List all rules in the selected chain | `iptables -L` |
| `iptables -A` | Append one or more rules to the end of the selected chain | `iptables -A INPUT -p tcp --dport 80 -j DROP` (Block incoming traffic on port 80) |
| `iptables -D` | Delete one or more rules from the selected chain | `iptables -D INPUT -p tcp --dport 80 -j DROP` (Remove rule blocking port 80) |
| `iptables -I` | Insert one or more rules in the selected chain | `iptables -I INPUT 1 -p tcp --dport 80 -j ACCEPT` (Insert rule to allow traffic on port 80 at the top) |
| `iptables -F` | Flush the selected chain (delete all rules in the chain) | `iptables -F` (Flush all rules) |
| `iptables -A INPUT -p tcp --dport 80 -j DROP` | Block incoming traffic on port 80 (HTTP) | `iptables -A INPUT -p tcp --dport 80 -j DROP` |
| `iptables -A INPUT -p tcp --dport 443 -j DROP` | Block incoming traffic on port 443 (HTTPS) | `iptables -A INPUT -p tcp --dport 443 -j DROP` |
| `iptables -A INPUT -p udp --dport 53 -j DROP` | Block incoming UDP traffic on port 53 (DNS) | `iptables -A INPUT -p udp --dport 53 -j DROP` |
| `iptables -A INPUT -s 192.168.1.100 -j DROP` | Block all incoming traffic from a specific IP address | `iptables -A INPUT -s 192.168.1.100 -j DROP` |
| `iptables -A INPUT -p icmp -j DROP` | Block all incoming ICMP (ping) requests | `iptables -A INPUT -p icmp -j DROP` |

## System Control (systemctl)
| Command | Description |
|---------|-------------|
| `systemctl start <service>` | Start a service |
| `systemctl stop <service>` | Stop a service |
| `systemctl restart <service>` | Restart a service |
| `systemctl status <service>` | Show the status of a service |
| `systemctl enable <service>` | Enable a service to start on boot |
| `systemctl disable <service>` | Disable a service from starting on boot |
| `systemctl is-enabled <service>` | Check if a service is enabled |
| `systemctl is-active <service>` | Check if a service is active |
