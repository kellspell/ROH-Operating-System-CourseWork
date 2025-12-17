# Week 2 Laboratory Journal: Command-Line Fundamentals

**Student Name:** Ezequiel Lino da Silva
**Course:** Operating Systems
**Week:** 2
**Date:** 17/12/2025

---

## Table of Contents
1. [Learning Goals](#learning-goals)
2. [Part 1: Warm-up](#part-1-warm-up)
3. [Part 2: Terminal Navigation & File System Operations](#part-2-terminal-navigation--file-system-operations)
4. [Part 3: Process Management](#part-3-process-management)
5. [Part 4: System Information Commands](#part-4-system-information-commands)
6. [Part 5: Final Challenge](#part-5-final-challenge)
7. [Reflection and Key Learnings](#reflection-and-key-learnings)

---

## Learning Goals

This laboratory session focused on three primary objectives:

1. **Navigate and manipulate files/directories using the terminal**: Mastering essential command-line operations for file system management
2. **Monitor and manage processes**: Understanding process creation, monitoring, and termination in Linux
3. **Retrieve system information**: Using various commands to gather system hardware and software details

---

## Part 1: Warm-up

### Overview
Initial warm-up exercises to familiarize with basic terminal commands.

### Commands Executed

#### 1. Print Working Directory
```bash
pwd
```
**Purpose**: Displays the absolute path of the current working directory
**My Output**: `/home/[username]`
**Observation**: This command helps identify current location in the file system hierarchy

#### 2. Display Current User
```bash
whoami
```
**Purpose**: Shows the currently logged-in username
**My Output**: `[username]`
**Use Case**: Useful when switching between users or confirming identity

#### 3. Display Current Date and Time
```bash
date
```
**Purpose**: Shows current system date and time
**My Output**: `[Date and time output]`
**Example**: `Tue Dec 17 14:30:45 GMT 2025`

#### 4. Clear Terminal Screen
```bash
clear
```
**Purpose**: Clears the terminal screen for better readability
**Alternative**: `Ctrl+L` keyboard shortcut
**Observation**: Doesn't delete command history, just clears visual display

### Key Learning Points
- These basic commands are essential for terminal navigation
- `pwd` is particularly useful when navigating deep directory structures
- `whoami` confirms user context, especially important before running privileged commands
- `clear` helps maintain organized workspace

---

## Part 2: Terminal Navigation & File System Operations

### Overview
Comprehensive exercises covering file system navigation, file/directory creation, manipulation, and management.

### Exercise 1: Print Current Working Directory
```bash
pwd
```
**Output**: `/home/[username]`
**Context**: Confirms starting location before navigation

### Exercise 2: Navigate to /tmp Directory
```bash
cd /tmp
pwd
```
**Purpose**: Change to temporary directory used for temporary file storage
**Output**: `/tmp`
**Observation**: `/tmp` directory is cleared on system reboot

### Exercise 3: List Files Including Hidden Files
```bash
ls -a
```
**Purpose**: Display all files including hidden files (those starting with `.`)
**Flags Used**:
- `-a`: Show all files, including hidden ones

**Observed Files**:
- Hidden files like `.`, `..`, and potentially `.X11-unix/`, `.ICE-unix/`
- Regular temporary files from various applications

**Alternative Commands**:
```bash
ls -la  # Long format with hidden files
ls -lah # Long format, hidden files, human-readable sizes
```

### Exercise 4: Create Directory Structure
```bash
mkdir lab_test
cd lab_test
mkdir alpha beta gamma
ls
```

**Purpose**: Create a parent directory with three subdirectories
**Commands Breakdown**:
- `mkdir lab_test`: Creates parent directory
- `cd lab_test`: Navigate into parent directory
- `mkdir alpha beta gamma`: Creates three subdirectories simultaneously
- `ls`: Verify directory creation

**Directory Structure Created**:
```
lab_test/
├── alpha/
├── beta/
└── gamma/
```

**Verification**:
```bash
ls -l
# Output shows three directories: alpha, beta, gamma
```

### Exercise 5: Create Text File in Alpha Directory
```bash
cd alpha
touch notes.txt
# Or create with content:
echo "This is a test note" > notes.txt
ls -l notes.txt
```

**Purpose**: Create a text file within the alpha subdirectory
**Methods Used**:
- `touch notes.txt`: Creates empty file
- `echo "content" > notes.txt`: Creates file with content

**Verification**:
```bash
cat notes.txt  # Display file contents
ls -l notes.txt # Show file details
```

**My File Content**: `[Document your content here]`

### Exercise 6: Copy notes.txt to Beta Directory
```bash
cp notes.txt ../beta/
ls ../beta/
```

**Purpose**: Duplicate file to another directory
**Path Explanation**:
- `../beta/`: Navigate up one level (`..`) then into beta directory

**Verification**:
```bash
ls ../beta/
cat ../beta/notes.txt
```

**Result**: notes.txt now exists in both alpha and beta directories

### Exercise 7: Move notes.txt from Alpha to Gamma
```bash
mv notes.txt ../gamma/
ls
ls ../gamma/
```

**Purpose**: Move (not copy) file from alpha to gamma directory
**Result**:
- notes.txt removed from alpha directory
- notes.txt now in gamma directory

**Current File Locations**:
- `beta/notes.txt` (copy)
- `gamma/notes.txt` (moved from alpha)
- `alpha/` (empty)

**Verification**:
```bash
ls alpha/    # Should be empty
ls gamma/    # Should show notes.txt
```

### Exercise 8: Delete File in Beta Directory
```bash
rm ../beta/notes.txt
ls ../beta/
```

**Purpose**: Remove the copied file from beta directory
**Result**: beta directory is now empty

**Verification**:
```bash
ls beta/  # Should show empty or "No such file"
```

**Warning**: `rm` permanently deletes files; no recycle bin in command line

### Exercise 9: Write Content to hello.txt
```bash
cd /tmp/lab_test
echo 'Hello Lab' > hello.txt
cat hello.txt
```

**Purpose**: Create file with specific content using output redirection
**Operator Explanation**:
- `>`: Redirects output to file (overwrites if exists)
- `>>`: Appends to file (preserves existing content)

**Verification**:
```bash
cat hello.txt
# Output: Hello Lab
```

**File Contents**: `Hello Lab`

### Exercise 10: Display First 3 Lines of /etc/passwd
```bash
head -n 3 /etc/passwd
```

**Purpose**: View beginning of system password file
**Command Breakdown**:
- `head`: Display beginning of file
- `-n 3`: Show first 3 lines
- `/etc/passwd`: System file containing user account information

**Example Output**:
```
root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
```

**Field Explanation**:
- Username:Password:UID:GID:UserInfo:HomeDir:Shell
- `x` indicates password is stored in `/etc/shadow`

### Exercise 11: Monitor Log File with tail -f
```bash
tail -f /var/log/syslog
# or
tail -f -n 5 /var/log/syslog
```

**Purpose**: Real-time monitoring of last 5 lines of log file
**Command Breakdown**:
- `tail -f`: Follow mode, displays new lines as they're added
- `-n 5`: Show last 5 lines

**Use Case**: Essential for monitoring system logs, debugging applications, tracking events

**To Exit**: Press `Ctrl+C`

**My Observations**:
```
[Document what types of log entries you observed]
```

**Alternative Logs to Monitor**:
```bash
tail -f /var/log/auth.log   # Authentication logs
tail -f /var/log/kern.log   # Kernel logs
```

### Mini-Challenge: Create Nested File Structure and Locate It

#### Task
Create a folder `my_lab` with a nested file structure, add a `readme.txt`, and locate it.

#### Solution
```bash
cd /tmp
mkdir -p my_lab/projects/2025/operating_systems
cd my_lab/projects/2025/operating_systems
echo "Operating Systems Lab - Week 2" > readme.txt
echo "Command-Line Fundamentals Practice" >> readme.txt
cat readme.txt
```

**Commands Used**:
- `mkdir -p`: Creates parent directories as needed (recursive)
- `echo >> file`: Appends content to file

**Directory Structure Created**:
```
my_lab/
└── projects/
    └── 2025/
        └── operating_systems/
            └── readme.txt
```

#### Locating the File

**Method 1: Using find command**
```bash
find /tmp/my_lab -name readme.txt
```
**Output**: `/tmp/my_lab/projects/2025/operating_systems/readme.txt`

**Method 2: Using locate (if updatedb has been run)**
```bash
locate readme.txt | grep my_lab
```

**Method 3: Using tree command**
```bash
tree /tmp/my_lab
```

**My File Path**: `/tmp/my_lab/projects/2025/operating_systems/readme.txt`

---

## Part 3: Process Management

### Overview
Understanding process lifecycle, monitoring, background/foreground execution, and process termination.

### Exercise 1: Create Background Process

#### Starting Background Process
```bash
sleep 100 &
```

**Purpose**: Run sleep command in background for 100 seconds
**Output**:
```
[1] 12345
```
- `[1]`: Job number
- `12345`: Process ID (PID)

**Observation**: Command returns immediately; shell is not blocked

**What is `sleep`?**: Command that delays for specified number of seconds

### Exercise 2: Find Process ID Using ps

```bash
ps aux | grep sleep
# or
ps -ef | grep sleep
# or more specific
ps -u $USER | grep sleep
```

**Purpose**: Display information about the sleep process
**Command Options**:
- `ps aux`: All processes for all users
- `ps -ef`: Full format listing
- `| grep sleep`: Filter for sleep processes

**Example Output**:
```
USER       PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
username 12345  0.0  0.0   5180   736 pts/0    S    14:30   0:00 sleep 100
```

**Field Meanings**:
- **PID**: Process ID (12345)
- **%CPU**: CPU usage percentage
- **%MEM**: Memory usage percentage
- **STAT**: Process state (S = sleeping)
- **COMMAND**: Command name

**My PID**: `[Document your PID]`

### Exercise 3: Observe System Activity with top

```bash
top
```

**Purpose**: Real-time system monitoring showing processes, CPU, and memory usage

**Key Information Displayed**:
- **Top Section**: System summary
  - Uptime, load averages
  - Total tasks and states
  - CPU usage breakdown
  - Memory and swap usage

- **Process List**: Active processes sorted by CPU usage
  - PID, USER, CPU%, MEM%, TIME, COMMAND

**Useful Keyboard Shortcuts in top**:
- `q`: Quit
- `k`: Kill process (enter PID)
- `M`: Sort by memory usage
- `P`: Sort by CPU usage
- `1`: Show individual CPU cores
- `h`: Help

**Observations During top**:
```
[Document what you observed:
- Load averages
- CPU usage
- Memory usage
- Top processes
]
```

**Finding sleep Process in top**:
- Located sleep process with PID 12345
- CPU usage: ~0%
- Memory usage: minimal

### Exercise 4: Kill the Sleep Process

```bash
kill 12345
# or
kill [PID_from_previous_step]
```

**Purpose**: Terminate the background sleep process
**Command**: `kill [PID]`

**Verification**:
```bash
ps aux | grep sleep
# Should not show the process anymore
```

**Kill Signal Types**:
```bash
kill -15 [PID]    # SIGTERM (graceful termination, default)
kill -9 [PID]     # SIGKILL (force kill, cannot be ignored)
kill -l           # List all available signals
```

**Best Practice**: Use `kill` (SIGTERM) first; only use `kill -9` if process doesn't respond

**Result**: Process terminated successfully

### Exercise 5: Suspend and Resume with nano

#### Starting nano Editor
```bash
nano test.txt
```

**Purpose**: Learn job control - suspending and resuming processes

#### Steps Performed:

**1. Start nano and type some content:**
```
Type some text in the editor...
```

**2. Suspend the Process:**
```
Press Ctrl+Z
```

**Output**:
```
[1]+  Stopped                 nano test.txt
```

**What Happened**: Process is suspended (not terminated), moved to background in stopped state

**3. Check Job Status:**
```bash
jobs
```

**Output**:
```
[1]+  Stopped                 nano test.txt
```

**Jobs List Explanation**:
- `[1]`: Job number
- `+`: Current job
- `Stopped`: Job state
- `nano test.txt`: Command

**4. Resume in Foreground:**
```bash
fg
# or
fg %1  # Specify job number
```

**Result**: nano editor returns to foreground, continue editing

**Alternative - Resume in Background:**
```bash
bg %1
```
*Note: nano requires terminal interaction, so `bg` wouldn't be practical here*

**5. Save and Exit:**
```
Ctrl+O (Write Out)
Enter (Confirm filename)
Ctrl+X (Exit)
```

### Exercise 6: Run Long Command in Background

```bash
sleep 300 &
# or
find / -name "*.log" 2>/dev/null &
```

**Purpose**: Demonstrate background execution with `&` operator

**Example with long-running command:**
```bash
find /usr -type f -name "*.conf" > config_files.txt &
```

**Output**:
```
[2] 12346
```

**Check Background Jobs:**
```bash
jobs
```

**Output**:
```
[1]-  Running                 sleep 300 &
[2]+  Running                 find /usr -type f -name "*.conf" > config_files.txt &
```

**Bring to Foreground if Needed:**
```bash
fg %2  # Bring job 2 to foreground
```

**Terminate Background Job:**
```bash
kill %2  # Kill job 2
```

### Mini-Challenge: Start, Find, and Kill Background Process

#### Complete Workflow

**Step 1: Start Background Command**
```bash
ping localhost > ping_output.txt &
```

**Output**:
```
[1] 12350
```

**Step 2: Find PID**
```bash
jobs -l
```
**Output**:
```
[1]+ 12350 Running                 ping localhost > ping_output.txt &
```

**Alternative methods:**
```bash
ps aux | grep ping
pgrep ping
pidof ping
```

**My PID**: `12350`

**Step 3: Monitor the Process**
```bash
ps -p 12350
tail -f ping_output.txt  # Watch output in real-time
```

**Step 4: Kill the Process**
```bash
kill 12350
```

**Verification**:
```bash
jobs
ps -p 12350  # Should show no process found
```

**Step 5: Check Output File**
```bash
cat ping_output.txt
wc -l ping_output.txt  # Count lines (number of pings captured)
```

**Challenge Completed Successfully**: ✓

---

## Part 4: System Information Commands

### Overview
Commands to retrieve hardware, kernel, and system resource information.

### Exercise 1: Display Kernel Information

```bash
uname -a
```

**Purpose**: Display all system information
**Output Example**:
```
Linux hostname 6.8.0-90-generic #90-Ubuntu SMP PREEMPT_DYNAMIC x86_64 GNU/Linux
```

**Information Breakdown**:
- **Linux**: Kernel name
- **hostname**: Network node hostname
- **6.8.0-90-generic**: Kernel release version
- **#90-Ubuntu SMP**: Kernel version details
- **x86_64**: Machine hardware architecture
- **GNU/Linux**: Operating system

**Alternative uname Options**:
```bash
uname -s  # Kernel name: Linux
uname -n  # Network node hostname
uname -r  # Kernel release: 6.8.0-90-generic
uname -m  # Machine hardware: x86_64
uname -o  # Operating system: GNU/Linux
```

**My System Information**:
```
[Document your specific output]
```

### Exercise 2: Check Number of CPUs

```bash
lscpu
```

**Purpose**: Display detailed CPU architecture information

**Key Information from Output**:
- **Architecture**: x86_64 (64-bit)
- **CPU(s)**: Total number of CPUs
- **Thread(s) per core**: Hyperthreading info
- **Core(s) per socket**: Physical cores
- **Socket(s)**: Number of physical processors
- **Model name**: CPU brand and model
- **CPU MHz**: Current frequency
- **Virtualization**: VT-x/AMD-V support

**Quick CPU Count Commands**:
```bash
lscpu | grep "^CPU(s):"
nproc  # Show number of processing units
cat /proc/cpuinfo | grep processor | wc -l
```

**My System CPU Information**:
- Total CPUs: `[X]`
- Cores per socket: `[X]`
- Model: `[CPU Model]`
- Architecture: `[x86_64 or other]`

### Exercise 3: Show Free Memory

```bash
free -h
```

**Purpose**: Display memory usage in human-readable format

**Example Output**:
```
              total        used        free      shared  buff/cache   available
Mem:          7.7Gi       2.1Gi       3.2Gi       156Mi       2.4Gi       5.1Gi
Swap:         2.0Gi          0B       2.0Gi
```

**Column Meanings**:
- **total**: Total installed RAM
- **used**: Memory currently used by processes
- **free**: Completely unused memory
- **shared**: Memory used by tmpfs
- **buff/cache**: Memory used for caching (can be freed if needed)
- **available**: Memory available for new applications

**Important**: Look at "available" not "free" for actual available memory

**Additional Memory Commands**:
```bash
free -m  # Display in megabytes
free -g  # Display in gigabytes
vmstat   # Virtual memory statistics
```

**My System Memory**:
- Total RAM: `[X GB]`
- Used: `[X GB]`
- Available: `[X GB]`
- Swap Total: `[X GB]`

### Exercise 4: Display Mounted Filesystems

```bash
df -h
```

**Purpose**: Show disk space usage for all mounted filesystems

**Example Output**:
```
Filesystem      Size  Used Avail Use% Mounted on
/dev/sda1        25G   12G   12G  50% /
tmpfs           3.9G     0  3.9G   0% /dev/shm
/dev/sda2       100G   45G   50G  47% /home
```

**Column Meanings**:
- **Filesystem**: Device or partition name
- **Size**: Total size
- **Used**: Space used
- **Avail**: Space available
- **Use%**: Percentage used
- **Mounted on**: Mount point

**Options**:
- `-h`: Human-readable sizes (GB, MB)
- `-T`: Show filesystem type
- `-i`: Show inode information

**Additional Disk Commands**:
```bash
df -hT  # Include filesystem type
du -sh /home  # Directory size summary
```

**My System Disk Usage**:
```
[Document your filesystem usage]
```

### Exercise 5: Display Block Devices

```bash
lsblk
```

**Purpose**: List all block devices (disks, partitions, optical drives)

**Example Output**:
```
NAME   MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT
sda      8:0    0   25G  0 disk
├─sda1   8:1    0   24G  0 part /
├─sda2   8:2    0    1K  0 part
└─sda5   8:5    0  975M  0 part [SWAP]
sr0     11:0    1 1024M  0 rom
```

**Column Meanings**:
- **NAME**: Device name
- **MAJ:MIN**: Major and minor device numbers
- **RM**: Removable device (1=yes, 0=no)
- **SIZE**: Device size
- **RO**: Read-only (1=yes, 0=no)
- **TYPE**: Device type (disk, part, rom)
- **MOUNTPOINT**: Where device is mounted

**Additional Options**:
```bash
lsblk -f  # Show filesystem type and UUID
lsblk -o NAME,SIZE,TYPE,MOUNTPOINT  # Custom columns
```

**My System Block Devices**:
```
[Document your block device structure]
```

### Exercise 6: See Logged-in Users

```bash
who
# or
w
```

**Purpose**: Display currently logged-in users

**who Output Example**:
```
username tty7         2025-12-17 14:00 (:0)
username pts/0        2025-12-17 14:15 (192.168.1.100)
```

**w Output Example** (more detailed):
```
 14:30:00 up  2:30,  2 users,  load average: 0.15, 0.25, 0.20
USER     TTY      FROM             LOGIN@   IDLE   JCPU   PCPU WHAT
username tty7     :0               14:00    2:30m  5:25   0.15s /usr/bin/gnome-shell
username pts/0    192.168.1.100    14:15    0.00s  0.04s  0.01s w
```

**Information Shown**:
- **USER**: Username
- **TTY**: Terminal type (tty = local, pts = pseudo-terminal)
- **FROM**: Remote hostname or display
- **LOGIN@**: Login time
- **IDLE**: Idle time
- **WHAT**: Current command

**Related Commands**:
```bash
users          # Simple list of usernames
last           # Login history
lastlog        # Last login for all users
```

**Currently Logged-in Users**:
```
[Document who is logged in]
```

### Exercise 7: Display System Uptime

```bash
uptime
```

**Purpose**: Show how long system has been running

**Example Output**:
```
14:30:00 up 2 days, 5:25, 2 users, load average: 0.15, 0.25, 0.20
```

**Information Breakdown**:
- **14:30:00**: Current time
- **up 2 days, 5:25**: System has been running for 2 days, 5 hours, 25 minutes
- **2 users**: Two users logged in
- **load average: 0.15, 0.25, 0.20**: System load for last 1, 5, and 15 minutes

**Understanding Load Average**:
- Number of processes waiting for CPU time
- On single-core system: 1.0 = 100% utilized
- On dual-core system: 2.0 = 100% utilized
- Lower is generally better

**My System Uptime**:
```
[Document your system uptime and load]
```

### Mini-Challenge: Find System Hostname, Uptime, and Available RAM

#### Complete Solution

```bash
# System Hostname
hostname
# or
hostnamectl
# or
cat /etc/hostname
```

**My Hostname**: `[Your hostname]`

```bash
# System Uptime
uptime
# or
uptime -p  # Pretty format: up 2 days, 5 hours, 25 minutes
# or
cat /proc/uptime  # Raw seconds
```

**My Uptime**: `[Your uptime]`

```bash
# Available RAM
free -h
# or extract just available RAM
free -h | grep Mem | awk '{print $7}'
```

**My Available RAM**: `[X GB]`

#### Combined Single Command

```bash
echo "=== System Information Report ==="
echo "Hostname: $(hostname)"
echo "Uptime: $(uptime -p)"
echo "Available RAM: $(free -h | grep Mem | awk '{print $7}')"
echo "Total RAM: $(free -h | grep Mem | awk '{print $2}')"
echo "Kernel: $(uname -r)"
```

**Challenge Output**:
```
=== System Information Report ===
Hostname: [your-hostname]
Uptime: up 2 days, 5 hours, 25 minutes
Available RAM: 5.1Gi
Total RAM: 7.7Gi
Kernel: 6.8.0-90-generic
```

**Challenge Completed Successfully**: ✓

---

## Part 5: Final Challenge

### Overview
Create comprehensive system report with multiple information sources and compress for archival.

### Task Breakdown

#### Step 1: Create Directory for Reports

```bash
cd ~
mkdir sys_report
ls -ld sys_report
```

**Purpose**: Create dedicated directory to store system information files
**Verification**: Directory created successfully in home directory

#### Step 2: Save Kernel Information

```bash
uname -a > sys_report/kernel.txt
cat sys_report/kernel.txt
```

**Purpose**: Capture complete kernel and system information
**Output Redirected**: All kernel details saved to `kernel.txt`

**File Contents**:
```
Linux hostname 6.8.0-90-generic #90-Ubuntu SMP PREEMPT_DYNAMIC x86_64 GNU/Linux
```

**Verification**:
```bash
ls -lh sys_report/kernel.txt
cat sys_report/kernel.txt
```

#### Step 3: Save Current Processes

```bash
ps aux > sys_report/processes.txt
head -20 sys_report/processes.txt
wc -l sys_report/processes.txt
```

**Purpose**: Capture snapshot of all running processes
**Information Captured**:
- All processes from all users
- CPU and memory usage
- Process states and IDs
- Command lines

**File Statistics**:
```bash
wc -l sys_report/processes.txt
# Output: [X] processes captured
```

**Sample Content Check**:
```bash
head -10 sys_report/processes.txt
```

#### Step 4: Save Memory Information

```bash
free -h > sys_report/memory.txt
cat sys_report/memory.txt
```

**Purpose**: Document current memory and swap usage
**Information Saved**:
- Total, used, and available RAM
- Buffer and cache usage
- Swap space information

**File Contents**:
```
              total        used        free      shared  buff/cache   available
Mem:          7.7Gi       2.1Gi       3.2Gi       156Mi       2.4Gi       5.1Gi
Swap:         2.0Gi          0B       2.0Gi
```

#### Step 5: Verify All Files Created

```bash
ls -lh sys_report/
```

**Expected Files**:
```
total 24K
-rw-rw-r-- 1 user user  123 Dec 17 14:30 kernel.txt
-rw-rw-r-- 1 user user  456 Dec 17 14:30 memory.txt
-rw-rw-r-- 1 user user  15K Dec 17 14:30 processes.txt
```

**File Count**:
```bash
ls sys_report/ | wc -l
# Output: 3
```

#### Step 6: Compress the sys_report Directory

```bash
tar -czf sys_report.tar.gz sys_report/
ls -lh sys_report.tar.gz
```

**Command Breakdown**:
- `tar`: Tape archive utility
- `-c`: Create archive
- `-z`: Compress with gzip
- `-f`: Specify filename
- `sys_report/`: Directory to archive

**Alternative Command with Verbose Output**:
```bash
tar -czvf sys_report.tar.gz sys_report/
```
- `-v`: Verbose (show files being archived)

**Verification**:
```bash
# Check archive was created
ls -lh sys_report.tar.gz

# Verify archive contents without extracting
tar -tzf sys_report.tar.gz

# Check compression ratio
du -sh sys_report/
du -sh sys_report.tar.gz
```

**My Archive Details**:
- Original size: `[X KB]`
- Compressed size: `[X KB]`
- Compression ratio: `[X%]`

#### Step 7: Extract and Verify Archive (Optional Testing)

```bash
# Create test directory
mkdir test_extract
cd test_extract

# Extract archive
tar -xzf ../sys_report.tar.gz

# Verify extraction
ls -R sys_report/
diff -r sys_report/ ../sys_report/
```

**Extraction Command Options**:
- `-x`: Extract archive
- `-z`: Decompress gzip
- `-f`: Specify filename

### Additional Enhancements (Optional)

#### Enhanced Report with More Details

```bash
# Add more system information files
cd ~/sys_report

# Disk usage
df -h > disk_usage.txt

# CPU information
lscpu > cpu_info.txt

# Network interfaces
ip addr > network_info.txt

# System uptime
uptime > uptime.txt

# Logged-in users
who > users.txt

# Re-compress with new files
cd ~
rm sys_report.tar.gz
tar -czf sys_report.tar.gz sys_report/
```

#### Create Report with Timestamp

```bash
# Include timestamp in filename
TIMESTAMP=$(date +%Y%m%d_%H%M%S)
tar -czf sys_report_${TIMESTAMP}.tar.gz sys_report/
```

**Result**: `sys_report_20251217_143000.tar.gz`

### Final Challenge Summary

**Tasks Completed**:
- ✓ Created sys_report directory
- ✓ Saved kernel information (uname -a)
- ✓ Saved process list (ps aux)
- ✓ Saved memory information (free -h)
- ✓ Compressed directory into tar.gz archive

**Files Generated**:
1. `sys_report/kernel.txt`
2. `sys_report/processes.txt`
3. `sys_report/memory.txt`
4. `sys_report.tar.gz` (compressed archive)

**Challenge Completed Successfully**: ✓

---

## Reflection and Key Learnings

### Skills Acquired

#### 1. Terminal Navigation Proficiency
- Mastered directory navigation with `cd`, `pwd`, `ls`
- Understood absolute vs relative paths
- Learned efficient navigation using `..`, `.`, `~`, `-` shortcuts
- Practiced file system exploration

#### 2. File and Directory Management
- Created complex directory structures with `mkdir -p`
- Manipulated files with `cp`, `mv`, `rm`
- Used redirection operators `>` and `>>`
- Understood importance of careful file deletion

#### 3. Process Management Skills
- Created background processes with `&`
- Monitored processes with `ps`, `top`, `jobs`
- Managed foreground/background execution with `fg`, `bg`
- Terminated processes using `kill` with appropriate signals
- Suspended and resumed processes with job control

#### 4. System Information Gathering
- Retrieved kernel details with `uname`
- Analyzed CPU architecture with `lscpu`
- Monitored memory usage with `free`
- Checked disk usage with `df` and block devices with `lsblk`
- Tracked logged-in users and system uptime

#### 5. Advanced Command-Line Techniques
- Piped commands with `|` for filtering
- Used output redirection for file creation
- Applied `grep` for filtering process information
- Employed command substitution with `$(command)`
- Created compressed archives with `tar`

### Key Concepts Understood

#### Process States
- **Running**: Actively executing on CPU
- **Sleeping**: Waiting for resources or events
- **Stopped**: Suspended by signal (Ctrl+Z)
- **Zombie**: Terminated but not yet reaped

#### Job Control
- **Foreground**: Process has terminal control
- **Background**: Process runs without terminal control
- **Suspension**: Temporarily stop process execution
- **Resumption**: Continue stopped process

#### Memory Management
- **Physical RAM**: Actual hardware memory
- **Virtual Memory**: Abstraction including swap
- **Buffers/Cache**: Temporary storage for performance
- **Available Memory**: Actually usable for new applications

#### File System Hierarchy
- `/tmp`: Temporary files (cleared on reboot)
- `/home`: User personal directories
- `/etc`: System configuration files
- `/var/log`: System log files

### Practical Applications

#### System Administration
- Monitor system resources to identify performance issues
- Track running processes to troubleshoot problems
- Manage background tasks for long-running operations
- Generate system reports for documentation

#### DevOps and Automation
- Background process management for automated tasks
- System information gathering for inventory
- Log file monitoring for application debugging
- Archive creation for backups and deployments

#### Development Workflow
- Run build processes in background
- Monitor application logs in real-time
- Manage multiple terminal sessions efficiently
- Create deployment archives

### Challenges Encountered and Solutions

**Challenge 1**: Understanding difference between `>` and `>>`
**Solution**:
- `>` overwrites file completely
- `>>` appends to existing content
- Practice with test files to see difference

**Challenge 2**: Finding correct PID for background process
**Solution**:
- Use multiple methods: `ps aux | grep`, `jobs -l`, `pgrep`
- Note PID immediately when starting background process
- Use `jobs` for job-based management instead of PIDs

**Challenge 3**: Understanding when to use `kill -9` vs `kill`
**Solution**:
- Always try `kill` (SIGTERM) first - allows graceful shutdown
- Only use `kill -9` (SIGKILL) for unresponsive processes
- SIGTERM allows process to clean up, SIGKILL does not

**Challenge 4**: Interpreting `free` output correctly
**Solution**:
- Focus on "available" column, not "free"
- Understand that buffers/cache can be freed if needed
- Linux uses excess RAM for caching - this is good, not bad

### Command Cheat Sheet Created

#### Navigation & Files
```bash
pwd                 # Print working directory
cd [dir]            # Change directory
ls -lah             # List all files with details
mkdir -p [path]     # Create directory with parents
touch [file]        # Create empty file
cp [src] [dest]     # Copy file
mv [src] [dest]     # Move/rename file
rm -rf [path]       # Remove recursively
```

#### Process Management
```bash
[command] &         # Run in background
ps aux              # List all processes
top                 # Interactive process viewer
jobs                # List background jobs
fg [%job]           # Bring to foreground
bg [%job]           # Resume in background
kill [PID]          # Terminate process
kill -9 [PID]       # Force kill process
Ctrl+Z              # Suspend current process
Ctrl+C              # Interrupt current process
```

#### System Information
```bash
uname -a            # All system information
lscpu               # CPU details
free -h             # Memory usage
df -h               # Disk usage
lsblk               # Block devices
who / w             # Logged-in users
uptime              # System uptime
hostname            # System name
```

#### File Operations
```bash
cat [file]          # Display file contents
head -n X [file]    # Show first X lines
tail -n X [file]    # Show last X lines
tail -f [file]      # Follow file updates
echo "text" > file  # Write to file (overwrite)
echo "text" >> file # Append to file
```

#### Archives
```bash
tar -czf file.tar.gz dir/   # Create compressed archive
tar -xzf file.tar.gz        # Extract archive
tar -tzf file.tar.gz        # List archive contents
```

### Comparison: GUI vs CLI

| Task | GUI Method | CLI Method | CLI Advantage |
|------|------------|------------|---------------|
| Copy File | Drag & drop / Right-click | `cp source dest` | Scriptable, faster for multiple files |
| Monitor Processes | Task Manager | `top`, `ps` | More detailed, scriptable, remote access |
| System Info | System Settings | `uname`, `lscpu`, `free` | Complete info, scriptable, precise |
| Archive Files | Right-click compress | `tar -czf` | More control, consistent, scriptable |
| Background Tasks | Launch & minimize | `command &` | True background, terminal independence |

### Best Practices Learned

1. **Always verify your location**: Use `pwd` before file operations
2. **Use tab completion**: Reduces typing errors and increases speed
3. **Test destructive commands**: Try `ls` before `rm` to verify targets
4. **Monitor system resources**: Regular checks prevent problems
5. **Name files descriptively**: Include dates, descriptions in filenames
6. **Document commands**: Keep notes of useful command combinations
7. **Use version control**: Git for important files and scripts
8. **Regular backups**: Archive important data with `tar`

### Questions for Further Exploration

1. How do process priorities (nice values) affect CPU scheduling?
2. What's the difference between soft and hard links in file systems?
3. How can I monitor network traffic from command line?
4. What are the security implications of running processes with sudo?
5. How do I create automated scripts for system monitoring?
6. What's the difference between terminal, console, shell, and command line?
7. How do I use regular expressions effectively with grep?
8. What are the best practices for log file rotation and management?

### Next Steps for Learning

1. **Shell Scripting**: Automate repetitive tasks with bash scripts
2. **Advanced Process Management**: Learn about nice, renice, nohup
3. **System Monitoring**: Explore htop, iotop, nethogs
4. **Log Analysis**: Master grep, awk, sed for log file analysis
5. **Networking Commands**: Study netstat, ss, tcpdump, nmap
6. **Package Management**: Deep dive into apt, dpkg
7. **Permissions and Ownership**: Advanced chmod, chown, ACLs
8. **Remote Access**: Learn ssh, scp, rsync

### Real-World Applications

#### Scenario 1: Server Monitoring
```bash
# Check if server is overloaded
uptime
free -h
df -h
ps aux --sort=-%mem | head -10  # Top memory users
```

#### Scenario 2: Application Debugging
```bash
# Monitor application logs in real-time
tail -f /var/log/application.log | grep ERROR
```

#### Scenario 3: System Backup
```bash
# Create timestamped backup
tar -czf backup_$(date +%Y%m%d).tar.gz /important/data/
```

#### Scenario 4: Process Management
```bash
# Start long-running job
nohup python train_model.py > training.log 2>&1 &
# Check progress
tail -f training.log
```

---

## Conclusion

This Week 2 laboratory session provided essential hands-on experience with command-line fundamentals. The exercises progressed from basic navigation to complex process management and system information gathering.

### Key Achievements

1. **Mastered Terminal Navigation**: Confidently navigate Linux file system structure
2. **File Management Proficiency**: Create, copy, move, and delete files and directories
3. **Process Control Skills**: Manage background processes, monitor system activity, control job execution
4. **System Analysis Capability**: Gather comprehensive system information using various commands
5. **Practical Application**: Created complete system report and compressed archive

### Significance of Command-Line Skills

The command-line interface is fundamental to:
- **Server Administration**: Most servers are managed via CLI
- **Automation**: Scripts require command-line knowledge
- **Remote Management**: SSH access provides CLI only
- **Efficiency**: Many tasks are faster via CLI than GUI
- **Troubleshooting**: CLI provides more detailed information
- **DevOps**: CI/CD pipelines rely on command-line tools

### Personal Growth

This laboratory reinforced that mastery comes through practice. Each command execution builds muscle memory and deepens understanding. The practical exercises demonstrated that the command line, while initially intimidating, becomes a powerful and efficient tool with experience.

The ability to monitor processes, manage resources, and gather system information are fundamental skills for anyone working with Linux systems, whether as system administrator, developer, or DevOps engineer.

---

**Laboratory Hours**: [X hours]
**Completion Date**: 17/12/2025
**Status**: ✓ Completed

---

**Note**: This journal documents the practical exercises from the Command-Line Fundamentals lab worksheet. Replace placeholder values in square brackets with your actual observations and outputs from performing the exercises.
