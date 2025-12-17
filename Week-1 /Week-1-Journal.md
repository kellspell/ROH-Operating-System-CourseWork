# Week 1 Laboratory Journal: Linux Environment Setup and Basic Commands

**Student Name:** Ezequiel Lino da Silva
**Course:** Operating Systems
**Week:** 1
**Date:** 17/12/2025 #Updated

---

## Table of Contents
1. [Learning Objectives](#learning-objectives)
2. [Requirements and Downloads](#requirements-and-downloads)
3. [Installation Process](#installation-process)
   - [VirtualBox Installation](#virtualbox-installation)
   - [Ubuntu Linux Installation](#ubuntu-linux-installation)
   - [Visual Studio Code Installation](#visual-studio-code-installation)
4. [Linux Commands Practice](#linux-commands-practice)
   - [Hardware Operations](#hardware-operations)
   - [File Commands](#file-commands)
   - [Package Installation](#package-installation)
   - [System Management and Information](#system-management-and-information)
   - [File Permission](#file-permission)
5. [Laboratory Exercise](#laboratory-exercise)
6. [Reflection and Key Learnings](#reflection-and-key-learnings)

---

## Learning Objectives

This laboratory session focused on four key objectives:

1. **To install Virtual Box on a computer system**: Understanding virtualization and setting up a virtual machine environment
2. **To install a Linux operating system within the virtual box environment**: Deploying Ubuntu Linux in a virtualized environment
3. **To install software (Visual Studio Code) on Linux operating systems**: Installing and configuring development tools on Linux
4. **To work with basic Linux commands**: Learning fundamental command-line operations for system navigation, file management, and system administration

---

## Requirements and Downloads

### Software Requirements

**VirtualBox**: Latest Desktop version
- Download Link: https://www.virtualbox.org/wiki/Downloads
- Purpose: Provides virtualization platform to run Linux within existing operating system
- Version used: [Note your version]

**Ubuntu Linux**: Latest Desktop version
- Download Link: http://www.ubuntu.com/download/desktop
- Purpose: Open-source Linux distribution for learning OS concepts
- Version used: [Note your version]

**Visual Studio Code**: Latest version
- Download Link: https://code.visualstudio.com/download
- Purpose: Modern code editor with Linux support
- Version used: [Note your version]

**Installation Guide**: https://www.makeuseof.com/install-ubuntu-virtualbox/

---

## Installation Process

### VirtualBox Installation

**Steps Completed:**
1. Downloaded VirtualBox installer for my host operating system
2. Ran the installer with administrator privileges
3. Followed installation wizard accepting default settings
4. Verified installation by launching VirtualBox application

**Observations:**
- Installation was straightforward
- VirtualBox creates a virtualization layer allowing multiple OS to run simultaneously
- The interface provides options for creating and managing virtual machines

**Challenges Encountered:** [Document any issues you faced]

**Solutions Applied:** [Document how you resolved them]

---

### Ubuntu Linux Installation

**Virtual Machine Configuration:**
- VM Name: [Your VM name]
- Memory (RAM): [e.g., 4096 MB]
- Processors: [e.g., 2 CPUs]
- Hard Disk: [e.g., 25 GB VDI dynamically allocated]

**Installation Steps:**
1. Created new virtual machine in VirtualBox
2. Configured VM settings (memory, processors, storage)
3. Attached Ubuntu ISO file as virtual optical drive
4. Started VM and followed Ubuntu installation wizard
5. Configured user account, hostname, and timezone
6. Completed installation and rebooted into Ubuntu

**Post-Installation Configuration:**
- Installed VirtualBox Guest Additions for better integration
- Configured screen resolution and shared folders
- Updated system packages using: `sudo apt update && sudo apt upgrade`

**Observations:**
- Ubuntu provides a user-friendly installation process
- The desktop environment (GNOME) is intuitive and modern
- System boots quickly in virtual environment

**Challenges Encountered:** [Document any issues]

**Solutions Applied:** [Document solutions]

---

### Visual Studio Code Installation

**Installation Methods:**
There are multiple ways to install VS Code on Linux. I used: [Choose your method]

**Method 1: Using .deb package (Debian/Ubuntu)**
```bash
# Download the .deb package from website
# Install using dpkg
sudo dpkg -i code_*.deb
sudo apt install -f  # Fix any dependency issues
```

**Method 2: Using APT repository**
```bash
# Add Microsoft GPG key and repository
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg
sudo install -o root -g root -m 644 packages.microsoft.gpg /etc/apt/trusted.gpg.d/
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/code stable main" > /etc/apt/sources.list.d/vscode.list'

# Update and install
sudo apt update
sudo apt install code
```

**Method 3: Using Snap**
```bash
sudo snap install --classic code
```

**Verification:**
- Launched VS Code from application menu or terminal (`code`)
- Verified version: [Note your version]
- Explored basic features and extensions

---

## Linux Commands Practice

### Hardware Operations

These commands provide information about system hardware components.

#### 1. Display bootup messages
```bash
dmesg
```
**Purpose**: Shows kernel ring buffer messages, useful for troubleshooting hardware issues
**Output Observations**: [Describe what you saw - boot sequence, hardware detection, drivers loaded]

**Example Output:**
```
[    0.000000] Linux version 5.x.x-generic
[    0.000000] Command line: BOOT_IMAGE=/boot/vmlinuz...
[    0.001234] CPU: Physical Processor ID: 0
```

#### 2. Display memory usage details
```bash
free -h
```
**Purpose**: Shows amount of free and used memory in human-readable format
**My System Memory:**
- Total: [e.g., 3.8 GB]
- Used: [e.g., 1.2 GB]
- Free: [e.g., 1.8 GB]
- Available: [e.g., 2.4 GB]

**Key Learning**: The `-h` flag displays values in human-readable format (GB, MB) rather than bytes

#### 3. Display information about block devices
```bash
lsblk
```
**Purpose**: Lists all block devices (hard drives, partitions, optical drives)
**Output Observations**:
- My system has [X] storage devices
- Primary disk: [e.g., /dev/sda with X GB]
- Partition layout: [Describe partitions]

#### 4. Display CPU details
```bash
cat /proc/cpuinfo
```
**Purpose**: Shows detailed CPU information
**My System CPU:**
- Model: [e.g., Intel Core i5]
- CPU cores: [e.g., 2]
- Architecture: [e.g., x86_64]
- CPU MHz: [e.g., 2400]

**Alternative command:** `lscpu` provides more formatted CPU information

#### 5. Outline hardware configuration details
```bash
lshw
```
or with sudo for full details:
```bash
sudo lshw
```
**Purpose**: Lists all hardware components in detail
**Note**: Requires root privileges for complete information
**Output Observations**: [Describe hardware detected - motherboard, memory modules, storage controllers, network interfaces]

#### 6. Display disk data details
```bash
hdparm -i /dev/sda
```
**Purpose**: Shows disk device information and parameters
**Note**: Replace `/dev/sda` with your actual disk device
**Key Information**: Model, serial number, firmware version, capabilities

#### 7. Display hardware information as stated in BIOS
```bash
sudo dmidecode
```
**Purpose**: Reads system DMI/SMBIOS table to display hardware information as firmware sees it
**Information includes**: BIOS details, system manufacturer, motherboard info, memory slots

#### 8. Display USB devices using tree-like format
```bash
lsusb -tv
```
**Purpose**: Shows USB devices connected to system in hierarchical tree format
**My Connected USB Devices**: [List devices you see]

#### 9. Display PCI devices using tree-like format
```bash
lspci -tv
```
**Purpose**: Shows PCI devices in tree format
**Devices Observed**: [e.g., graphics controller, network controller, storage controller]

#### 10. Execute read-speed test on device/disk
```bash
sudo hdparm -tT /dev/sda
```
**Purpose**: Tests disk read performance
**My Results:**
- Cached reads: [X MB/sec]
- Buffered disk reads: [X MB/sec]

**Note**: Performance varies based on virtual vs physical disk

---

### File Commands

File commands are essential for navigating and managing the Linux file system.

#### 1. List files in the directory
```bash
ls
```
**Purpose**: Lists files and directories in current directory
**Common Options:**
- `ls -l`: Long format with permissions, owner, size, date
- `ls -h`: Human-readable file sizes
- `ls -t`: Sort by modification time
- `ls -r`: Reverse order

**Practice Output**: [What you saw when running in different directories]

#### 2. List all files including hidden files
```bash
ls -a
```
**Purpose**: Shows all files including hidden files (starting with `.`)
**Observations**: Hidden files often include configuration files like `.bashrc`, `.profile`

**Combined options:**
```bash
ls -lah
```
Shows long format, all files, human-readable sizes

#### 3. Display current directory
```bash
pwd
```
**Purpose**: "Print Working Directory" - shows absolute path of current location
**Example Output:** `/home/username/Documents`

**Key Learning**: Understanding absolute vs relative paths is crucial in Linux

#### 4. Create a new directory
```bash
mkdir [directory name]
mkdir my_directory
```
**Purpose**: Creates new directory
**Practice Examples:**
```bash
mkdir test_folder
mkdir -p parent/child/grandchild  # Creates nested directories
mkdir dir1 dir2 dir3  # Creates multiple directories
```

#### 5. Remove a file
```bash
rm [file name]
rm test.txt
```
**Purpose**: Deletes specified file
**WARNING**: Deletion is permanent; no recycle bin in command line
**Safe Practice**: Use `rm -i` for interactive confirmation

#### 6. Remove a directory recursively
```bash
rm -r [directory name]
```
**Purpose**: Removes directory and all its contents
**Options:**
- `-r`: Recursive (required for non-empty directories)
- `-f`: Force (no confirmation)
- `-i`: Interactive (asks before each deletion)

#### 7. Remove a directory without requiring confirmation recursively
```bash
rm -rf [directory name]
```
**Purpose**: Force removes directory and contents without prompts
**DANGER**: Extremely powerful and dangerous command; use with caution
**Best Practice**: Always double-check path before using `-rf`

#### 8. Copy the contents of one file to another file
```bash
cp [file name 1] [file name 2]
cp source.txt destination.txt
```
**Purpose**: Copies file to new location or name
**Options:**
- `-i`: Interactive (prompt before overwrite)
- `-v`: Verbose (show what's being copied)
- `-p`: Preserve file attributes (permissions, timestamps)

#### 9. Copy the contents of one file to a second file recursively
```bash
cp -r [directory name 1] [directory name 2]
```
**Purpose**: Copies entire directory structure
**Use Case**: Backing up directories, duplicating project structures

#### 10. Rename [file name 1] to [file name 2]
```bash
mv [file name 1] [file name 2]
mv old_name.txt new_name.txt
```
**Purpose**: Moves or renames files and directories
**Dual Function:**
- Same directory: Renames file
- Different directory: Moves file

**Example:**
```bash
mv file.txt /home/user/Documents/  # Moves file
mv old.txt new.txt  # Renames file
```

#### 11. Create a new file using touch
```bash
touch [file name]
touch newfile.txt
```
**Purpose**: Creates empty file or updates timestamp of existing file
**Use Cases:**
- Quickly create empty files
- Update file modification time
- Create multiple files: `touch file1 file2 file3`

#### 12. Display the contents of a file
```bash
more [file name]
cat [file name]
```
**Difference:**
- `cat`: Displays entire file at once
- `more`: Displays file page by page (use space to advance, q to quit)
- Alternative: `less` (more features than `more`)

**Example:**
```bash
cat /etc/os-release  # Shows OS information
more /var/log/syslog  # Views log file page by page
```

#### 13. Append file contents to another file
```bash
cat [file name 1] >> [file name 2]
```
**Purpose**: Adds contents of file1 to end of file2
**Important Distinction:**
- `>`: Overwrites destination file
- `>>`: Appends to destination file

**Example:**
```bash
cat log1.txt >> combined.txt
cat log2.txt >> combined.txt
```

#### 14. Display the first 10 lines of a file
```bash
head [file name]
head -n 5 [file name]  # First 5 lines
```
**Purpose**: Shows beginning of file
**Use Cases:**
- Quick preview of large files
- View file headers
- Check log file formats

#### 15. Display the last 10 lines of a file
```bash
tail [file_name]
tail -n 20 [file_name]  # Last 20 lines
tail -f [file_name]  # Follow mode (real-time updates)
```
**Purpose**: Shows end of file
**Special Use:** `tail -f` is invaluable for monitoring log files in real-time

#### 16. Encrypt a file
```bash
gpg -c [file_name]
```
**Purpose**: Encrypts file using symmetric encryption
**Process:**
1. Command prompts for passphrase
2. Creates encrypted file with `.gpg` extension
3. Original file remains (delete manually if needed)

#### 17. Decrypt a file
```bash
gpg [file_name.gpg]
```
**Purpose**: Decrypts GPG-encrypted file
**Process:**
1. Prompts for passphrase
2. Outputs decrypted file (removes `.gpg` extension)

#### 18. Show the number of words, lines, and bytes in a file
```bash
wc [file_name]
wc -l [file_name]  # Lines only
wc -w [file_name]  # Words only
wc -c [file_name]  # Bytes only
```
**Purpose**: "Word Count" - provides file statistics
**Output Format:** `lines words bytes filename`

**Example:**
```bash
wc document.txt
# Output: 150 890 5234 document.txt
```

#### 19. List number of lines/words/characters in each file in a directory
```bash
ls | xargs wc
```
**Purpose**: Combines listing files with word count
**How it works:**
- `ls` lists files
- `|` (pipe) passes output to next command
- `xargs` converts input to arguments for `wc`
- `wc` counts lines/words/bytes for each file

**Key Learning**: Introduction to piping and command chaining

#### 20. Overwrite a file to prevent its recovery
```bash
shred -u [filename]
```
**Purpose**: Securely deletes file by overwriting data multiple times
**Options:**
- `-u`: Remove file after overwriting
- `-n`: Number of overwrite passes
- `-z`: Final overwrite with zeros to hide shredding

**Use Case**: Secure deletion of sensitive data

---

### Package Installation

Linux uses package managers to install, update, and remove software.

#### 1. Install a package using APT (Ubuntu/Debian)
```bash
apt install [package name]
sudo apt install [package name]
```
**Purpose**: APT (Advanced Package Tool) manages software on Debian-based systems
**Note**: Requires `sudo` (superuser privileges)

**Example:**
```bash
sudo apt install vim
sudo apt install htop
```

**Process:**
1. APT contacts repositories
2. Resolves dependencies
3. Downloads package
4. Installs and configures

#### 2. Install an .rpm package from local file
```bash
rpm -i [package name.rpm]
```
**Purpose**: RPM (Red Hat Package Manager) for Red Hat-based systems
**Note**: Used on Fedora, CentOS, RHEL (not typically on Ubuntu)

#### 3. Remove an .rpm package
```bash
rpm -e [package name.rpm]
```
**Purpose**: Removes RPM package from system

#### 4. Install software from source code
```bash
tar zxvf [source_code.tar.gz]
cd [source_code]
./configure
make
make install
```
**Purpose**: Compiles and installs software from source
**Steps Explained:**
1. `tar zxvf`: Extracts compressed archive
2. `./configure`: Checks system and configures build
3. `make`: Compiles source code
4. `make install`: Installs compiled binaries

**When Used:** Software not available in package repositories or needing custom compilation

#### 5. Install a package using DNF
```bash
dnf install [package name.rpm]
```
**Purpose**: DNF (Dandified YUM) - modern package manager for Fedora
**Relationship:** DNF replaced YUM as the default package manager

#### 6. List all installed packages with YUM
```bash
yum list installed
```
**Purpose**: Shows all packages installed on system
**Useful For:** Auditing installed software, checking versions

#### 7. Display package information
```bash
yum info [package name]
```
**Purpose**: Shows detailed information about specific package
**Information Includes:** Version, repository, size, description, dependencies

#### 8. Find a package by keyword
```bash
yum search [keyword]
```
**Purpose**: Searches package repositories for keyword
**Use Case:** Finding package name when you know functionality but not exact name

#### 9. Install a package using YUM
```bash
yum install [package name.rpm]
```
**Purpose**: YUM (Yellowdog Updater Modified) package manager
**Note:** Largely replaced by DNF but still available

**Ubuntu vs Fedora/Red Hat Package Managers:**
- Ubuntu/Debian: APT (apt, apt-get, dpkg)
- Fedora/Red Hat: DNF/YUM (dnf, yum, rpm)
- Both accomplish same goals with different tools

---

### System Management and Information

These commands provide information about the system and enable system control.

#### 1. Display system information using uname
```bash
uname -r  # Kernel release
uname -a  # All information
```
**Purpose**: Shows system information
**Options:**
- `-r`: Kernel release version
- `-s`: Kernel name
- `-n`: Network node hostname
- `-m`: Machine hardware name
- `-a`: All available information

**My System Information:** [Note your output]

#### 2. Display system uptime
```bash
uptime
```
**Purpose**: Shows how long system has been running and load average
**Output Includes:**
- Current time
- System uptime
- Number of users logged in
- Load averages (1, 5, 15 minutes)

**Example Output:** `14:32:15 up 2 days, 5:23, 1 user, load average: 0.25, 0.30, 0.28`

#### 3. See system hostname
```bash
hostname
```
**Purpose**: Displays system's network name
**Related:** `hostname -f` shows fully qualified domain name

#### 4. Show the IP address of the system
```bash
hostname -i
```
**Purpose**: Displays IP address(es) associated with hostname
**Alternative:** `ip addr` or `ifconfig` (deprecated but still widely used)

**My System IP:** [Note your IP address]

#### 5. List system reboot history
```bash
last reboot
```
**Purpose**: Shows history of system reboots from system logs
**Use Case:** Tracking system stability, investigating unexpected reboots

#### 6. See current time and date
```bash
date
```
**Purpose**: Displays current system date and time
**Options:**
- `date +%Y-%m-%d`: Custom format (e.g., 2024-01-15)
- `date +%s`: Unix timestamp (seconds since 1970)

#### 7. Query and change the system clock
```bash
timedatectl
```
**Purpose**: Displays and controls system time and date settings
**Information Shown:**
- Local time
- Universal time (UTC)
- RTC (hardware clock) time
- Timezone
- NTP synchronization status

**Change timezone example:**
```bash
timedatectl set-timezone America/New_York
```

#### 8. Show current calendar
```bash
cal
```
**Purpose**: Displays calendar for current month
**Options:**
- `cal 2024`: Full year
- `cal 3 2024`: Specific month and year (March 2024)
- `cal -3`: Previous, current, and next month

#### 9. List logged in users
```bash
w
```
**Purpose**: Shows who is logged in and what they're doing
**Information Includes:**
- Username
- Terminal
- Login time
- Idle time
- Current process

**Alternative:** `who` (less detailed)

#### 10. See which user you are using
```bash
whoami
```
**Purpose**: Displays current username
**Use Case:** Confirming identity when switching users or using sudo

**Related:** `id` shows user ID, group ID, and group memberships

#### 11. Show information about a particular user
```bash
finger [username]
```
**Purpose**: Displays information about user account
**Note:** May need to install: `sudo apt install finger`
**Information:** Login name, full name, home directory, shell, login time

**Alternative:** `cat /etc/passwd | grep username`

#### 12. Shut down the system immediately
```bash
shutdown now
```
**Purpose**: Immediately powers off the system
**Requires:** Root privileges (`sudo shutdown now`)

**Options:**
- `shutdown -h now`: Halt (power off)
- `shutdown -r now`: Reboot
- `shutdown -h +10`: Shutdown in 10 minutes
- `shutdown -c`: Cancel scheduled shutdown

**Alternatives:**
- `poweroff`: Immediate shutdown
- `reboot`: Restart system
- `halt`: Stop system

---

### File Permission

Linux uses a permission system to control access to files and directories.

#### Permission Basics

**Permission Types:**
- **r (read)**: View file contents or list directory contents (value: 4)
- **w (write)**: Modify file or create/delete files in directory (value: 2)
- **x (execute)**: Run file as program or enter directory (value: 1)

**Permission Groups:**
- **Owner (u)**: File creator/owner
- **Group (g)**: Users in file's group
- **Others (o)**: All other users

**Permission Format:**
```
-rwxr-xr--
```
- First character: File type (`-` = file, `d` = directory, `l` = link)
- Next 3: Owner permissions (rwx)
- Next 3: Group permissions (r-x)
- Last 3: Others permissions (r--)

#### Numeric Permission Representation

Permissions can be represented as octal numbers:
- Read (r) = 4
- Write (w) = 2
- Execute (x) = 1

**Calculation:**
- rwx = 4+2+1 = 7
- rw- = 4+2+0 = 6
- r-x = 4+0+1 = 5
- r-- = 4+0+0 = 4

#### 1. Assign read, write, and execute permission to everyone
```bash
chmod 777 [file name]
```
**Breakdown:**
- First 7: Owner permissions (rwx = 4+2+1)
- Second 7: Group permissions (rwx = 4+2+1)
- Third 7: Others permissions (rwx = 4+2+1)

**Result:** Everyone can read, write, and execute the file

**WARNING:** 777 is generally insecure; grants full access to all users

#### 2. Give read, write, and execute permission to owner, and read and execute permission to group and others
```bash
chmod 755 [file name]
```
**Breakdown:**
- 7 (rwx): Owner can read, write, execute
- 5 (r-x): Group can read and execute (not write)
- 5 (r-x): Others can read and execute (not write)

**Common Use:** Executable scripts and programs

#### 3. Assign full permission to owner, and read and write permission to group and others
```bash
chmod 766 [file name]
```
**Breakdown:**
- 7 (rwx): Owner has full permissions
- 6 (rw-): Group can read and write (not execute)
- 6 (rw-): Others can read and write (not execute)

**Use Case:** Shared files where multiple users need to modify but not execute

#### Symbolic Permission Method

Alternative to numeric method:
```bash
chmod u+x [file name]      # Add execute for owner
chmod g-w [file name]      # Remove write from group
chmod o=r [file name]      # Set others to read only
chmod a+r [file name]      # Add read for all (a = all)
```

**Symbols:**
- `u` = user (owner), `g` = group, `o` = others, `a` = all
- `+` = add permission, `-` = remove permission, `=` = set exactly

#### 4. Change the ownership of a file
```bash
chown [user] [file name]
sudo chown john document.txt
```
**Purpose**: Changes file owner
**Requires:** Root privileges (sudo)
**Use Case:** Transferring file ownership after creation or copying

#### 5. Change the owner and group ownership of a file
```bash
chown [user]:[group] [file name]
sudo chown john:developers project.txt
```
**Purpose**: Changes both owner and group simultaneously
**Format:** `user:group`

**Example:**
```bash
sudo chown alice:staff report.pdf
```

**Recursive option:**
```bash
chown -R [user]:[group] [directory]
sudo chown -R john:developers /project
```
Changes ownership of directory and all contents

#### Viewing Permissions

```bash
ls -l [file name]
```
Shows detailed file information including permissions

**Example Output:**
```
-rw-r--r-- 1 john developers 1024 Jan 15 10:30 document.txt
```
- `-rw-r--r--`: Permissions
- `john`: Owner
- `developers`: Group
- `1024`: Size in bytes
- `Jan 15 10:30`: Modification date/time
- `document.txt`: Filename

---

## Laboratory Exercise

This section documents the completion of the practical exercise from the laboratory note.

### Exercise Tasks

#### Task 1: Navigate to /etc directory and list contents
```bash
cd /etc
ls
```
**Observations:**
- The `/etc` directory contains system configuration files
- Notable files observed: [List some files you saw]
- File types: Configuration files, system scripts, network settings

**Selected Files Examined:**
```bash
cat /etc/os-release      # Operating system information
more /etc/hosts          # Host name resolution
head /etc/passwd         # User account information
```

#### Task 2: Check rest of filesystem tree
```bash
# Explored /bin directory
cd /bin
ls
pwd
```
**Observations:**
- `/bin`: Essential user command binaries (ls, cp, cat, bash, etc.)

```bash
# Explored /usr/bin directory
cd /usr/bin
ls | head -20
```
**Observations:**
- `/usr/bin`: User binaries and applications
- Contains most user programs

```bash
# Explored /sbin directory
cd /sbin
ls
```
**Observations:**
- `/sbin`: System administration binaries
- Requires root privileges for most commands (fsck, reboot, ifconfig)

```bash
# Explored /tmp directory
cd /tmp
ls
```
**Observations:**
- `/tmp`: Temporary files
- Cleared on reboot
- World-writable directory

```bash
# Explored /boot directory
cd /boot
ls
```
**Observations:**
- `/boot`: Boot loader files
- Contains kernel images, initial RAM disk
- Critical for system startup

#### Task 3: Return to home directory
```bash
cd
# or
cd ~
# or
cd $HOME
```
**Verification:**
```bash
pwd
```
**Output:** `/home/[username]`

#### Task 4: Create directory "folder_1"
```bash
mkdir folder_1
```
**Verification:**
```bash
ls -ld folder_1
```

#### Task 5: Navigate into the folder
```bash
cd folder_1
pwd
```
**Output:** `/home/[username]/folder_1`

#### Task 6: Create file "test_1"
```bash
touch test_1
```
**Verification:**
```bash
ls -l test_1
```

#### Task 7: Open file and add content
```bash
# Using nano editor
nano test_1
```
**Content Added:**
```
This is a test file created during Week 1 laboratory exercise.
Operating Systems Course - Linux Basics
Date: [Date]
```
**Saved using:** Ctrl+O (write out), Enter, Ctrl+X (exit)

**Alternative methods:**
```bash
# Using echo and redirection
echo "This is test content" > test_1

# Using vim
vim test_1
```

#### Task 8: Copy "test_1" to "test_2"
```bash
cp test_1 test_2
```
**Verification:**
```bash
ls -l
cat test_2
```
**Result:** Both files exist with identical content

#### Task 9: Return to home directory
```bash
cd
# or
cd ..
```
**Verification:**
```bash
pwd
```

#### Task 10: Create directory "folder_2"
```bash
mkdir folder_2
```
**Verification:**
```bash
ls -ld folder_2
```

#### Task 11: Copy "test_1" from "folder_1" to "test_1" in "folder_2"
```bash
cp folder_1/test_1 folder_2/test_1
```
**Alternative using absolute paths:**
```bash
cp ~/folder_1/test_1 ~/folder_2/test_1
```
**Verification:**
```bash
ls -l folder_2/
cat folder_2/test_1
```

#### Task 12: Compare "test_1" in "folder_2" to "test_2" in "folder_1"
```bash
diff folder_2/test_1 folder_1/test_2
```
**Result:** [No output = files are identical]

**Alternative comparison methods:**
```bash
# Using cmp (byte-by-byte comparison)
cmp folder_2/test_1 folder_1/test_2

# Using diff with side-by-side display
diff -y folder_2/test_1 folder_1/test_2
```

**Observations:**
- `test_1` (source) was copied to both `test_2` in folder_1 and `test_1` in folder_2
- All three files contain identical content
- `diff` returns no output when files are identical

#### Task 13: Schedule system shutdown in 10 minutes
```bash
sudo shutdown -h +10
```
**Output:**
```
Shutdown scheduled for [time], use 'shutdown -c' to cancel.
```

**Verification:**
```bash
# Check scheduled shutdown
shutdown --show
```

**To cancel (for this exercise):**
```bash
sudo shutdown -c
```
**Output:** `Shutdown cancelled.`

**Alternative scheduling:**
```bash
# Shutdown at specific time
sudo shutdown -h 18:00

# Shutdown with message
sudo shutdown -h +10 "System maintenance in 10 minutes"
```

#### Task 14: Put the system on again
**Note:** After shutdown, system needs to be powered on via:
- VirtualBox: Click "Start" on the VM
- Physical machine: Press power button

**Not applicable in this exercise as shutdown was cancelled**

#### Task 15: List all directories and files created
```bash
# From home directory
cd ~
ls -R folder_1 folder_2
```

**Complete structure:**
```
folder_1/
├── test_1
└── test_2

folder_2/
└── test_1
```

**Detailed listing:**
```bash
ls -lh folder_1/
ls -lh folder_2/
```

**Tree view (if tree is installed):**
```bash
tree folder_1 folder_2
```

### Exercise Cleanup (Optional)
```bash
# Remove created directories and files
rm -r folder_1 folder_2

# Verification
ls folder_1 folder_2  # Should show "No such file or directory"
```

---

## Reflection and Key Learnings

### Technical Skills Acquired

1. **Virtualization Understanding**
   - Learned how VirtualBox creates isolated virtual machines
   - Understood resource allocation (CPU, memory, storage) for VMs
   - Recognized advantages: testing without affecting host OS, running multiple OS simultaneously

2. **Linux Installation Experience**
   - Gained hands-on experience with Ubuntu installation process
   - Learned about disk partitioning and boot loaders
   - Understood importance of Guest Additions for VM integration

3. **Command Line Proficiency**
   - Developed comfort with terminal-based interaction
   - Learned filesystem navigation (cd, pwd, ls)
   - Practiced file manipulation (cp, mv, rm, touch)
   - Explored system information commands

4. **Linux File System Structure**
   - Understood hierarchical directory organization
   - Learned purpose of key directories (/etc, /bin, /home, /tmp)
   - Recognized difference between system and user directories

5. **Permission System Comprehension**
   - Learned read/write/execute permission model
   - Understood owner/group/others permission groups
   - Practiced numeric (777) and symbolic (u+x) permission notation

### Challenges Encountered and Solutions

**Challenge 1:** [Describe a specific challenge you faced]
**Solution:** [How you resolved it]

**Challenge 2:** [Another challenge]
**Solution:** [Resolution]

### Key Insights

1. **Linux Philosophy**: Everything is a file, including hardware devices (visible in /dev directory)

2. **Command Power**: Simple commands can be combined (piping) to perform complex operations

3. **Case Sensitivity**: Linux is case-sensitive; "File.txt" and "file.txt" are different files

4. **No Confirmation**: Many commands (rm, mv) don't ask for confirmation; must be careful

5. **Permission Model**: Security is built into the file system through permissions; proper permission management is crucial

6. **Package Management**: Centralized software installation through package managers is more secure than downloading executables

### Comparison: Linux vs Windows

| Aspect | Linux | Windows |
|--------|-------|---------|
| **File System** | Case-sensitive, single root (/) | Case-insensitive, multiple roots (C:, D:) |
| **Command Line** | bash, terminal | cmd, PowerShell |
| **File Paths** | Forward slashes (/) | Backslashes (\\) |
| **Software Installation** | Package managers (apt, dnf) | Executable installers (.exe, .msi) |
| **File Deletion** | Immediate (no Recycle Bin from CLI) | Recycle Bin available |
| **Permissions** | Owner/Group/Others with rwx | ACLs (Access Control Lists) |
| **Root/Admin** | sudo for elevated privileges | UAC prompts |

### Practical Applications

1. **System Administration**: Commands learned are foundational for server management
2. **DevOps**: Terminal proficiency essential for automation and scripting
3. **Software Development**: Linux environment commonly used for development
4. **Cybersecurity**: Understanding permissions and system structure crucial for security

### Next Steps for Learning

1. **Shell Scripting**: Automate repetitive tasks using bash scripts
2. **Advanced File Operations**: Learn grep, find, sed, awk for text processing
3. **Process Management**: Understand ps, top, kill, systemctl
4. **Networking Commands**: Explore ping, netstat, ssh, scp
5. **Package Management**: Deep dive into apt, dpkg, snap
6. **System Monitoring**: Learn about logs (/var/log), system resources, performance

### Questions for Further Exploration

1. How do Linux permissions compare to ACLs in terms of security and flexibility?
2. What are the performance differences between physical and virtual Linux installations?
3. How does the Linux boot process work from BIOS to login prompt?
4. What are the advantages of different shell environments (bash, zsh, fish)?
5. How can I contribute to open-source Linux projects?

---

## Conclusion

This Week 1 laboratory session provided essential hands-on experience with Linux systems. The practical exercises reinforced theoretical knowledge about operating systems, file management, and command-line interfaces.

Key achievements:
- Successfully set up a virtualized Linux environment
- Gained confidence with Linux command-line operations
- Understood Linux file system structure and navigation
- Learned essential system administration commands
- Practiced file and directory management
- Explored hardware information commands
- Understood Linux permission model

The foundation established in this laboratory will be crucial for more advanced operating system topics in subsequent weeks, including process management, memory management, inter-process communication, and system security.

Linux's open-source nature, powerful command-line tools, and widespread use in servers and development environments make it an essential skill for computer science students. The hands-on approach of this laboratory reinforced that reading about commands is different from actually using them—practical experience is irreplaceable.

---

**Laboratory Hours:** [X hours]
**Completion Date:** [Date]
**Status:** ✓ Completed

---

**Note:** This journal should be customized with your actual observations, outputs, challenges, and insights from performing the laboratory exercises. Replace placeholder text (in square brackets) with your specific information.
