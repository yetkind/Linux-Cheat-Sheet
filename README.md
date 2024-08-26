# Linux Command Cheat Sheet (Extended Version)

This cheat sheet is designed to help both beginners and advanced users quickly find and use the most common Linux commands. 
It includes basic commands, file management, process control, network management, system monitoring, and more. 

---

## Basic Commands

### **Navigation and File Operations**
| Command | Description |
| ------- | ----------- |
| `pwd` | Print the current working directory. |
| `ls` | List files and directories in the current directory. Use `ls -la` for detailed view. |
| `cd [directory]` | Change to the specified directory. Use `cd ..` to go up one level. |
| `mkdir [directory]` | Create a new directory. |
| `rmdir [directory]` | Remove an empty directory. |
| `cp [source] [destination]` | Copy files or directories. Use `cp -r` for recursive copy (including directories). |
| `mv [source] [destination]` | Move or rename files and directories. |
| `rm [file]` | Remove a file. Use `rm -r [directory]` to remove directories recursively. |
| `touch [file]` | Create a new empty file or update the timestamp of an existing file. |
| `cat [file]` | Display the content of a file. |
| `less [file]` | View the content of a file one screen at a time. Press `q` to quit. |
| `head [file]` | Display the first 10 lines of a file. Use `head -n [number] [file]` to specify the number of lines. |
| `tail [file]` | Display the last 10 lines of a file. Use `tail -f [file]` to follow updates to a file (e.g., logs). |

### **Text Processing**
| Command | Description |
| ------- | ----------- |
| `grep [pattern] [file]` | Search for a pattern in a file. Use `grep -r [pattern] [directory]` for recursive search. |
| `sed 's/[old]/[new]/g' [file]` | Find and replace text in a file using `sed`. |
| `awk '{print $1}' [file]` | Extract specific columns from a file or text stream using `awk`. |
| `cut -d '[delimiter]' -f [fields] [file]` | Extract sections from each line of a file based on delimiters. |
| `sort [file]` | Sort the contents of a file. |
| `uniq [file]` | Filter out duplicate lines in a file. Combine with `sort` for unique sorting. |
| `wc [file]` | Count the number of lines, words, and characters in a file. Use `wc -l` for line count only. |

### **File Permissions**
| Command | Description |
| ------- | ----------- |
| `chmod [permissions] [file]` | Change the permissions of a file or directory. |
| `chown [owner]:[group] [file]` | Change the owner and group of a file or directory. |
| `umask [mask]` | Set default file creation permissions. |

## System Information and Monitoring

### **System Information**
| Command | Description |
| ------- | ----------- |
| `uname -a` | Display system information, including kernel version and architecture. |
| `hostname` | Display the system's hostname. |
| `uptime` | Show how long the system has been running. |
| `df -h` | Show disk usage of all mounted filesystems in a human-readable format. |
| `du -sh [directory]` | Show the disk usage of a specific directory. |
| `free -h` | Display memory usage in a human-readable format. |
| `lscpu` | Display CPU architecture information. |
| `lsblk` | List block devices (e.g., hard drives). |
| `lsusb` | List USB devices connected to the system. |
| `lspci` | List PCI devices. |

### **Process Management**
| Command | Description |
| ------- | ----------- |
| `ps aux` | List all running processes. |
| `top` | Display real-time system resource usage. Press `q` to quit. |
| `htop` | Enhanced version of `top` with more features. Press `F10` to quit. |
| `kill [PID]` | Terminate a process by its process ID (PID). Use `kill -9 [PID]` for forceful termination. |
| `pkill [name]` | Terminate processes by name. |
| `bg` | Resume a suspended job in the background. |
| `fg` | Bring a job to the foreground. |
| `jobs` | List all jobs. |
| `nice -n [priority] [command]` | Run a command with a modified priority. |
| `renice [priority] [PID]` | Change the priority of an already running process. |

### **User Management**
| Command | Description |
| ------- | ----------- |
| `whoami` | Display the current user. |
| `id [username]` | Display user ID and group ID information for a user. |
| `adduser [username]` | Create a new user. |
| `passwd [username]` | Change the password of a user. |
| `deluser [username]` | Delete a user account. |
| `usermod -aG [group] [username]` | Add a user to a group. |
| `groups [username]` | List the groups a user belongs to. |

### **Network Management**
| Command | Description |
| ------- | ----------- |
| `ip a` or `ifconfig` | Display network interfaces and IP addresses. |
| `ping [host]` | Test connectivity to a host. |
| `traceroute [host]` | Trace the path packets take to a network host. |
| `netstat -tuln` | Show open ports and listening services. |
| `ss -tuln` | Alternative to `netstat`, showing open ports and listening services. |
| `curl -I [URL]` | Fetch HTTP headers from a URL. |
| `wget [URL]` | Download files from the internet. |
| `scp [source] [destination]` | Securely copy files between hosts. |
| `rsync -avz [source] [destination]` | Synchronize files between hosts with compression and progress display. |
| `ssh [user]@[host]` | Connect to a remote server via SSH. Use `-p [port]` to specify a non-default port. |

## Package Management

### **Debian/Ubuntu-based Systems (APT)**
| Command | Description |
| ------- | ----------- |
| `sudo apt update` | Update the package list. |
| `sudo apt upgrade` | Upgrade all installed packages to their latest versions. |
| `sudo apt install [package]` | Install a new package. |
| `sudo apt remove [package]` | Remove a package. |
| `sudo apt autoremove` | Remove unused packages automatically. |
| `sudo apt search [package]` | Search for a package in the repositories. |

### **Red Hat/CentOS-based Systems (YUM/DNF)**
| Command | Description |
| ------- | ----------- |
| `sudo yum update` or `sudo dnf update` | Update the package list and upgrade packages. |
| `sudo yum install [package]` or `sudo dnf install [package]` | Install a new package. |
| `sudo yum remove [package]` or `sudo dnf remove [package]` | Remove a package. |
| `sudo yum search [package]` or `sudo dnf search [package]` | Search for a package. |

### **Arch Linux-based Systems (Pacman)**
| Command | Description |
| ------- | ----------- |
| `sudo pacman -Syu` | Update the package list and upgrade packages. |
| `sudo pacman -S [package]` | Install a new package. |
| `sudo pacman -R [package]` | Remove a package. |
| `sudo pacman -Ss [package]` | Search for a package. |

## Filesystem Management

### **Mounting and Unmounting**
| Command | Description |
| ------- | ----------- |
| `mount [device] [mount_point]` | Mount a device to a directory. |
| `umount [mount_point]` | Unmount a device from a directory. |
| `df -hT` | Show mounted filesystems with their types and usage. |
| `blkid` | Display block device attributes (e.g., UUID, filesystem type). |

### **Disk Management**
| Command | Description |
| ------- | ----------- |
| `fdisk -l` | List disk partitions and sizes. |
| `parted` | Tool for creating and modifying disk partitions. |
| `mkfs.ext4 [partition]` | Format a partition with the ext4 filesystem. |
| `fsck [device]` | Check and repair a filesystem. |
| `mount -o loop [iso_file] [mount_point]` | Mount an ISO file as a loop device. |

## Archiving and Compression

### **Tar/Gzip**
| Command | Description |
| ------- | ----------- |
| `tar -cvf [archive.tar] [file/dir]` | Create a tar archive. |
| `tar -xvf [archive.tar]` | Extract a tar archive. |
| `tar -czvf [archive.tar.gz] [file/dir]` | Create a gzipped tar archive. |
| `tar -xzvf [archive.tar.gz]` | Extract a gzipped tar archive. |

### **Zip/Unzip**
| Command | Description |
| ------- | ----------- |
| `zip [archive.zip] [file/dir]` | Create a zip archive. |
| `unzip [archive.zip]` | Extract a zip archive. |

### **Bzip2/Bunzip2**
| Command | Description |
| ------- | ----------- |
| `bzip2 [file]` | Compress a file with bzip2. |
| `bunzip2 [file.bz2]` | Decompress a bzip2 file. |

## Scripting and Automation

### **Shell Scripting**
| Command | Description |
| ------- | ----------- |
| `#!/bin/bash` | Start a bash script. |
| `echo [text]` | Print text to the terminal. |
| `read [variable]` | Read input from the user and store it in a variable. |
| `$(command)` | Capture the output of a command. |
| `if [ condition ]; then ... fi` | Basic if-else statement. |
| `for [variable] in [list]; do ... done` | For loop to iterate over a list. |
| `while [ condition ]; do ... done` | While loop to execute commands as long as the condition is true. |

### **Cron Jobs**
| Command | Description |
| ------- | ----------- |
| `crontab -e` | Edit the cron jobs for the current user. |
| `* * * * * [command]` | Run a command on a schedule. Format: `minute hour day month day_of_week`. |
| `crontab -l` | List all cron jobs for the current user. |
| `service cron start/stop/restart` | Manage the cron service. |

## Advanced Commands

### **SSH Tunneling**
| Command | Description |
| ------- | ----------- |
| `ssh -L [local_port]:[remote_host]:[remote_port] [user]@[host]` | Create a local SSH tunnel. |
| `ssh -R [remote_port]:[local_host]:[local_port] [user]@[host]` | Create a remote SSH tunnel. |

### **Background and Screen**
| Command | Description |
| ------- | ----------- |
| `[command] &` | Run a command in the background. |
| `nohup [command] &` | Run a command immune to hangups and in the background. |
| `screen` | Start a screen session (persistent terminal session). |
| `screen -r` | Reattach to a detached screen session. |

### **Symbolic Links**
| Command | Description |
| ------- | ----------- |
| `ln -s [target] [link_name]` | Create a symbolic (soft) link. |
| `ln [target] [link_name]` | Create a hard link. |

### **Disk Quotas**
| Command | Description |
| ------- | ----------- |
| `quota -u [username]` | Display user disk quotas. |
| `setquota [username] [soft limit] [hard limit] [blocks] [inodes]` | Set disk quotas for a user. |


Feel free to customize and extend this cheat sheet as you explore more advanced Linux topics!
