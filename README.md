# Operating Systems Course Journal
## A Comprehensive Study Guide

**Course:** Operating Systems
**Academic Period:** October 2025
**Status:** Weeks 1-7 Complete

---

## 📹 Linux Demonstration Video

Watch the complete Linux system demonstration showcasing the practical implementation of concepts covered in this course:

**[🎬 Watch Linux Demonstration Video Here](https://vimeo.com/1145579534)**


**What's covered in the video:**
- Linux command-line operations and shell scripting
- System administration tasks and automation
- Security configurations and hardening
- Process management and monitoring
- File system operations and permissions

---

## About This Journal

This journal book serves as a comprehensive reference for the Operating Systems course, documenting key concepts, principles, and practical applications learned throughout the semester. Each week builds upon previous knowledge, creating a progressive understanding of operating system design, implementation, and management.

---

## How to Use This Guide

- **Navigate by Week:** Jump to specific weekly journals using the links in each part
- **Topic Reference:** Use the detailed chapter breakdowns to find specific subjects
- **Progressive Learning:** Follow the weeks in order for structured learning
- **Quick Reference:** Use bullet points for rapid topic lookup

---

## Table of Contents

### [Part I: Foundations and Linux Environment](#part-i-foundations-and-linux-environment)
**Week 1** - [Linux Environment Setup and Basic Commands](Main/Week-1-Journal.md)

### [Part II: Linux System Architecture](#part-ii-linux-system-architecture)
**Week 2** - [Command-Line Fundamentals](Main/Week-2-Journal.md)

### [Part III: Performance and Distribution Comparison](#part-iii-performance-and-distribution-comparison)
**Week 3** - [Linux Distribution Comparison and Performance Monitoring](Main/Week-3-Journal.md)

### [Part IV: System Planning and Architecture](#part-iv-system-planning-and-architecture)
**Week 4** - [System Planning and Distribution Selection](Main/Week-4-Journal.md)

### [Part V: Inter-Process Communication](#part-v-inter-process-communication)
**Week 5** - [Inter-Process Communication (IPC)](Main/Week-5-Journal.md)

### [Part VI: Security Fundamentals](#part-vi-security-fundamentals)
**Week 7** - [Process Management and Initial Security Configuration](Main/Week-7-Journal.md)

---

# Part I: Foundations and Linux Environment

## Week 1: [Linux Environment Setup and Basic Commands](Main/Week-1-Journal.md)

**Focus:** Setting up virtualized Linux environment and mastering fundamental command-line operations

### Chapter 1: Learning Objectives
- Install VirtualBox on a computer system
- Install Linux operating system (Ubuntu) within VirtualBox
- Install software (Visual Studio Code) on Linux
- Work with basic Linux commands

### Chapter 2: Requirements and Downloads
- **VirtualBox:** Latest desktop version for virtualization
- **Ubuntu Linux:** Latest desktop version
- **Visual Studio Code:** Modern code editor with Linux support
- Installation guides and resources

### Chapter 3: Installation Process
- **VirtualBox Installation**
  - Installation steps and verification
  - Virtualization layer configuration
- **Ubuntu Linux Installation**
  - VM configuration (memory, processors, storage)
  - Post-installation setup
  - VirtualBox Guest Additions
- **Visual Studio Code Installation**
  - Installation methods (.deb package, APT repository, Snap)
  - Verification and basic configuration

### Chapter 4: Linux Commands - Hardware Operations
- `dmesg`: Display bootup messages
- `free -h`: Memory usage details
- `lsblk`: Block devices information
- `cat /proc/cpuinfo`: CPU details
- `lshw`: Hardware configuration
- `hdparm`: Disk data details
- `dmidecode`: BIOS hardware information
- `lsusb -tv`: USB devices in tree format
- `lspci -tv`: PCI devices in tree format
- Performance testing commands

### Chapter 5: Linux Commands - File Operations
- File listing and navigation (`ls`, `pwd`)
- Directory management (`mkdir`, `cd`)
- File manipulation (`rm`, `cp`, `mv`, `touch`)
- File viewing (`cat`, `more`, `head`, `tail`)
- File encryption/decryption (`gpg`)
- File statistics (`wc`)
- Secure file deletion (`shred`)

### Chapter 6: Linux Commands - Package Installation
- **APT** (Ubuntu/Debian): `apt install`, package management
- **RPM/YUM/DNF** (Red Hat-based): Package installation and management
- Source code compilation and installation
- Package searching and information

### Chapter 7: Linux Commands - System Management
- System information (`uname`, `hostname`, `uptime`)
- Network information (`hostname -i`, `ip addr`)
- User information (`whoami`, `who`, `w`, `finger`)
- System time management (`date`, `timedatectl`, `cal`)
- System control (`shutdown`, `reboot`, `halt`)

### Chapter 8: File Permissions
- Permission basics (read, write, execute)
- Permission groups (owner, group, others)
- Numeric representation (755, 766, 777)
- Symbolic permission method (`chmod u+x`, `chmod g-w`)
- Ownership management (`chown`, `chgrp`)
- Recursive permission changes

### Chapter 9: Laboratory Exercise
- Navigate /etc directory and explore system files
- Check filesystem tree (/bin, /usr/bin, /sbin, /tmp, /boot)
- Create directory and file structures
- Practice file operations (copy, move, compare)
- Schedule system operations
- Document directory and file structures

### Chapter 10: Key Learnings and Reflection
- Virtualization understanding
- Linux installation experience
- Command-line proficiency
- File system structure knowledge
- Permission system comprehension

---

# Part II: Linux System Architecture

## Week 2: [Command-Line Fundamentals](Main/Week-2-Journal.md)

**Focus:** Mastering terminal navigation, process management, and system information gathering

### Chapter 1: Learning Goals
- Navigate and manipulate files/directories using the terminal
- Monitor and manage processes effectively
- Retrieve system information using command-line tools

### Chapter 2: Warm-up Commands
- `pwd`: Print working directory
- `whoami`: Display current user
- `date`: Show current date and time
- `clear`: Clear terminal screen

### Chapter 3: Terminal Navigation & File System Operations
- Directory navigation (`cd`, `pwd`)
- File listing with options (`ls -a`, `ls -l`, `ls -lah`)
- Creating directory structures (`mkdir`, `mkdir -p`)
- File creation and manipulation (`touch`, `echo`)
- File operations (`cp`, `mv`, `rm`)
- File viewing (`cat`, `more`, `less`, `head`, `tail`)
- Real-time file monitoring (`tail -f`)
- Nested directory creation and navigation

### Chapter 4: Process Management
- **Background Processes**
  - Running processes in background (`command &`)
  - Listing background jobs (`jobs`)
  - Process ID (PID) identification
- **Process Monitoring**
  - Static process listing (`ps aux`, `ps -ef`)
  - Real-time monitoring (`top`)
  - Enhanced monitoring (`htop`)
- **Process Control**
  - Suspending processes (Ctrl+Z)
  - Foreground/background switching (`fg`, `bg`)
  - Process termination (`kill`, `killall`)
  - Signal types (SIGTERM, SIGKILL)
  - Process priority (`nice`)

### Chapter 5: Process States and Lifecycle
- **Process States:**
  - Running (R): Executing or ready to run
  - Sleeping (S): Waiting for event (interruptible)
  - Sleeping (D): Waiting for I/O (uninterruptible)
  - Zombie (Z): Completed but parent hasn't read exit status
  - Stopped (T): Stopped by job control signal
- **Process Lifecycle:** New → Ready → Running → Waiting → Terminated
- Process hierarchy (`pstree`)

### Chapter 6: System Information Commands
- **Kernel and System Information**
  - `uname -a`: Complete system information
  - Kernel version, architecture, hostname
- **CPU Information**
  - `lscpu`: Detailed CPU architecture
  - CPU cores, threads, model, frequency
- **Memory Information**
  - `free -h`: Memory and swap usage
  - Understanding memory columns (total, used, free, available)
- **Disk Information**
  - `df -h`: Filesystem disk space usage
  - Mounted filesystems and usage percentages
- **Block Devices**
  - `lsblk`: List block devices and partitions
  - Device hierarchy and mount points
- **Network Information**
  - `ip addr`: Network interface configuration
  - Interface status, IP addresses, MAC addresses
- **User and Uptime Information**
  - `who`/`w`: Logged-in users
  - `uptime`: System uptime and load averages

### Chapter 7: Final Challenge - System Report
- Creating system report directory
- Capturing kernel information
- Saving process listings
- Recording memory information
- Creating compressed archives (`tar -czf`)
- Verification and extraction

### Chapter 8: Command Cheat Sheet
- Navigation and file commands
- Process management commands
- System information commands
- Archive operations

### Chapter 9: Key Learnings and Best Practices
- Terminal proficiency development
- Process control skills
- System monitoring capabilities
- Command-line efficiency techniques

---

# Part III: Performance and Distribution Comparison

## Week 3: [Linux Distribution Comparison and Performance Monitoring](Main/Week-3-Journal.md)

**Focus:** Comparing Linux distributions and analyzing system performance

### Chapter 1: Learning Objectives
- Explore and compare multiple Linux distributions
- Use performance monitoring tools to evaluate system metrics
- Document and reflect on system performance data

### Chapter 2: Distribution Setup and Exploration
- Launch multiple virtual machines with different distributions
- Compare package managers (APT, DNF, YUM, Pacman)
- Examine default services and init systems
- Analyze directory structures and configurations
- Distribution comparison matrix

### Chapter 3: Package Manager Comparison
- **APT** (Debian/Ubuntu):
  - Update, install, remove, search commands
  - Package cache and repositories
- **DNF/YUM** (Fedora/Red Hat):
  - Package management commands
  - Repository configuration
- **Pacman** (Arch):
  - Package operations
  - AUR (Arch User Repository)
- Package manager efficiency comparison

### Chapter 4: Default Services and Init Systems
- systemd initialization
- Service management and status
- Default running services comparison
- Boot time analysis

### Chapter 5: Performance Monitoring Tools
- **htop Installation and Usage**
  - Color-coded interface
  - Real-time CPU and memory monitoring
  - Process tree view
- **iotop Installation and Usage**
  - Disk I/O monitoring
  - Process I/O statistics
  - I/O bottleneck identification
- **nmon Installation and Usage**
  - Comprehensive system monitoring
  - Resource utilization patterns
  - Performance data collection

### Chapter 6: Performance Testing Scenarios
- **Idle System State**
  - Baseline CPU, memory, I/O usage
  - Resource consumption at rest
- **System Updates**
  - Resource usage during package updates
  - Network and disk activity
  - Process spawning patterns
- **File Copy Operations**
  - I/O performance measurement
  - Disk read/write speeds
  - Buffer cache behavior

### Chapter 7: Performance Metrics Analysis
- CPU efficiency comparison
- Memory management effectiveness
- I/O performance characteristics
- Boot time comparison
- Resource overhead analysis

### Chapter 8: Distribution Efficiency Reflection
- Performance winner determination
- Strengths and weaknesses identification
- Use case recommendations:
  - Lightweight/resource-constrained environments
  - Server/enterprise workloads
  - Development workstations
  - High-I/O applications

### Chapter 9: Documentation and Screenshots
- Capturing performance data
- Tool output interpretation
- Comparative analysis presentation

### Chapter 10: Key Insights
- Distribution selection criteria
- Performance vs. usability trade-offs
- System optimization opportunities
- Workload-specific recommendations

---

# Part IV: System Planning and Architecture

## Week 4: [System Planning and Distribution Selection](Main/Week-4-Journal.md)

**Focus:** Planning OS deployment, architectural design, and technical decision justification

### Chapter 1: System Architecture Design
- **Network Topology**
  - VirtualBox virtualization environment
  - Linux Server configuration
  - Linux Workstation configuration
  - Network connectivity design
- **System Components**
  - Server resources (CPU, RAM, storage)
  - Workstation resources
  - Network adapter configuration
- **Architecture Rationale**
  - Isolation and communication requirements
  - Security considerations
  - Flexibility and maintainability

### Chapter 2: Distribution Selection Justification
- **Selection Criteria**
  - Stability and long-term support
  - Community and documentation
  - Package management ecosystem
  - Hardware compatibility
  - Industry relevance
- **Ubuntu Server 22.04 LTS Analysis**
  - Advantages: LTS support, extensive documentation, large community
  - Disadvantages: Resource usage, perceived bloat
  - Use case suitability
- **Alternative Distributions**
  - CentOS Stream/Rocky Linux comparison
  - Debian comparison
  - Arch Linux comparison
- **Final Selection Rationale**

### Chapter 3: Workstation Configuration Decision
- **Configuration Options**
  - Full Desktop Environment (Ubuntu Desktop)
  - Minimal GUI Installation (Server + Lightweight DE)
  - CLI-Only Workstation
- **Ubuntu Desktop Selection**
  - Advantages: User-friendly, productivity tools, development-ready
  - Disadvantages: Resource intensive, overhead
  - Justification: Course requirements, learning efficiency
- **Alternative Analysis**
  - Lightweight DE trade-offs
  - CLI-only limitations
- **Decision Rationale**

### Chapter 4: Network Configuration
- **VirtualBox Networking**
  - NAT Network configuration
  - IP addressing scheme
  - Port forwarding setup
- **Network Options Comparison**
  - NAT Network (selected)
  - Bridged Adapter
  - Host-Only Adapter
- **Firewall Configuration**
  - UFW (Uncomplicated Firewall) setup
  - Rule configuration
  - Network testing procedures

### Chapter 5: System Specifications Documentation
- **Command: `uname -a`**
  - Kernel version and architecture
  - System information interpretation
- **Command: `free -h`**
  - Physical memory analysis
  - Swap space configuration
  - Memory utilization assessment
- **Command: `df -h`**
  - Filesystem disk usage
  - Partition structure
  - Storage analysis
- **Command: `ip addr`**
  - Network interface configuration
  - IP address assignment
  - Interface status
- **Command: `lsb_release -a`**
  - Distribution information
  - Release version and codename
  - LTS support details

### Chapter 6: Server vs. Workstation Comparison
- Resource allocation differences
- Storage requirements
- Memory usage patterns
- Desktop environment overhead
- System specifications summary table

### Chapter 7: Technical Decisions Summary
- Architecture design choices
- Distribution selection reasoning
- Resource allocation justification
- Network configuration rationale

### Chapter 8: Key Learnings
- System architecture understanding
- Distribution evaluation skills
- Virtual networking knowledge
- System documentation practices
- Justified decision-making

---

# Part V: Inter-Process Communication

## Week 5: [Inter-Process Communication (IPC)](Main/Week-5-Journal.md)

**Focus:** IPC mechanisms, shared memory, message passing, pipes, signals, and synchronization

### Chapter 1: Introduction to IPC
- **Definition:** Mechanism enabling cooperating processes to exchange data
- **Why Processes Need Communication:**
  - Information sharing among processes
  - Computation speedup through parallelism
  - Modularity in software design
  - Convenience in process interaction
- **Real-world Examples:**
  - Web browsers with separate processes for tabs
  - Shell pipelines for data processing
  - Client-server applications

### Chapter 2: IPC Models Overview
- **Shared Memory Model**
  - High-speed direct memory access
  - Requires explicit synchronization
  - Best for performance-critical applications
- **Message Passing Model**
  - Kernel-mediated communication
  - Built-in synchronization
  - Simpler to manage
- **Key Decision Factor:** Speed vs. simplicity trade-off

### Chapter 3: Shared Memory Systems
- **Concept and Advantages**
  - Fastest IPC method
  - Efficient for large data transfers
  - Zero-copy communication
- **Challenges**
  - Complex synchronization requirements
  - Security risks
  - Race condition prevention
- **Producer-Consumer Example**
  - Shared buffer coordination
  - Synchronization requirements
  - Data integrity maintenance

### Chapter 4: Message Passing Systems
- **Concept:** Communication via explicit messages
- **System Calls:** `send()` and `receive()`
- **Direct Communication**
  - Explicit process naming
  - Tight coupling between processes
- **Indirect Communication**
  - Mailboxes/ports for loose coupling
  - Multiple process sharing
- **Client-Server Example**
  - Request-response pattern
  - Web browser and server communication

### Chapter 5: Pipes and Redirection in Unix
- **Unix Philosophy:** Small, modular, composable programs
- **Pipe (|):** Connecting stdout to stdin
- **Redirection Operators**
  - Output redirection (`>`, `>>`)
  - Input redirection (`<`)
- **How Pipes Work:** Unidirectional data flow
- **Practical Examples:** Command chaining

### Chapter 6: Pipes, FIFOs, and Sockets
- **Pipes (Anonymous)**
  - Unnamed, in-memory communication
  - Related processes (parent-child)
  - Temporary existence
  - Created with `pipe()` system call
- **FIFOs (Named Pipes)**
  - Named files in filesystem
  - Unrelated process communication
  - Persistent until deleted
  - Created with `mkfifo()` system call
- **Sockets**
  - Network-capable endpoints
  - Local or remote communication
  - TCP/UDP protocol support
  - Bidirectional communication

### Chapter 7: Signals and Process Communication
- **Definition:** Asynchronous notifications
- **Common Signals:**
  - SIGINT: Ctrl+C graceful termination
  - SIGKILL: Forceful termination (uncatchable)
  - SIGTERM: Termination request (catchable)
- **Process Management**
  - Parent-child signal communication
  - Event notification
  - Process control
- **`kill()` System Call:** Sending signals to processes

### Chapter 8: Synchronization Primitives
- **Semaphores**
  - Counter-based resource control
  - Binary and counting semaphores
  - Process blocking until resource available
- **Mutexes**
  - Mutual exclusion locks
  - Binary locking (locked/unlocked)
  - Critical section protection
- **Monitors**
  - High-level synchronization constructs
  - Encapsulated shared data
  - Condition synchronization
- **Importance:** Prevent race conditions, ensure data consistency

### Chapter 9: IPC in Practice
- **Real-world Applications:**
  - Databases: Shared memory cache management
  - Web servers: Multi-process request handling
  - OS components: Kernel-daemon communication
  - Microservices: Distributed system communication
- **Performance Considerations:**
  - Kernel involvement overhead
  - Data transfer size impact
  - Communication frequency effects
  - Local vs. network communication

### Chapter 10: Laboratory Exercises
- **Task 1.1: Pipes and Redirection**
  - Standard streams manipulation
  - Output redirection to files
  - Command pipelines
  - Complex pipeline construction
- **Task 1.2: Named Pipes (FIFOs)**
  - Creating FIFOs with `mkfifo`
  - Producer-consumer pattern
  - Bidirectional communication
  - FIFO cleanup
- **Task 1.3: Process Signals**
  - Listing available signals
  - Signal operations (SIGTERM, SIGKILL)
  - Suspend and resume operations
  - Signal handling scripts
- **Task 1.4: File-Based IPC**
  - Producer and consumer scripts
  - Lockfile synchronization
  - Race condition management

### Chapter 11: Review and Key Concepts
- Shared memory vs. message passing trade-offs
- Pipe and FIFO differences
- Socket capabilities
- Signal types and handling
- Synchronization necessity
- IPC mechanism selection criteria

---

# Part VI: Security Fundamentals

## Week 7: [Process Management and Initial Security Configuration](Main/Week-7-Journal.md)

**Focus:** Process lifecycle, SSH security, firewall configuration, and user management

### Chapter 1: Learning Objectives
- Understand process lifecycle and states
- Use command-line tools for process monitoring
- Manage system processes effectively
- Implement coursework security controls

### Chapter 2: Process Fundamentals and Management
- **Exploring Process States**
  - `ps aux`: All running processes
  - `ps -ef`: Alternative process listing
  - `top`: Real-time monitoring
  - `htop`: Enhanced monitoring with colors
- **Process States:**
  - Running (R), Sleeping (S, D)
  - Zombie (Z), Stopped (T)
- **Process Relationships**
  - `pstree`: Process hierarchy visualization
  - Parent-child relationships
  - Process tree structure

### Chapter 3: Process Control Operations
- **Background Process Management**
  - Running processes in background (`&`)
  - Listing jobs (`jobs`)
  - Process ID tracking
- **Process Control**
  - Suspending (Ctrl+Z)
  - Foreground/background switching (`fg`, `bg`)
  - When to use foreground vs. background
- **Process Termination**
  - `kill [PID]`: Graceful termination (SIGTERM)
  - `kill -9 [PID]`: Forceful kill (SIGKILL)
  - `killall`: Terminate by name
  - Graceful vs. forceful termination
- **Process Priority**
  - `nice -n [value]`: Set process priority
  - Nice values (-20 to 19)
  - Priority impact on scheduling

### Chapter 4: Process Lifecycle
- **Lifecycle Stages:**
  1. New: Process creation
  2. Ready: Waiting for CPU time
  3. Running: Currently executing
  4. Waiting: Awaiting I/O or event
  5. Terminated: Execution finished
- State transition diagram
- Process state changes and triggers

### Chapter 5: SSH Key-Based Authentication
- **Generating SSH Keys**
  - `ssh-keygen -t ed25519`
  - Private and public key pair
  - Passphrase protection
- **Why ed25519 Over RSA:**
  - Smaller key size (256 bits)
  - Better security level
  - Faster operations
  - Modern cryptography
- **Copying Keys to Server**
  - `ssh-copy-id` command
  - Testing passwordless login
  - Key authentication mechanism
- **SSH Hardening**
  - Backup original configuration
  - Disable password authentication
  - Enable public key authentication
  - Disable root login
  - Restart SSH service

### Chapter 6: Security Configuration Benefits
- **PasswordAuthentication no**
  - Prevents brute-force attacks
  - Forces key-based authentication
- **PubkeyAuthentication yes**
  - Cryptographically secure authentication
- **PermitRootLogin no**
  - Prevents direct root access
  - Requires privilege escalation
  - Creates audit trail

### Chapter 7: Firewall Configuration
- **UFW (Uncomplicated Firewall)**
  - Check status: `sudo ufw status`
  - Installation if needed
- **Default Policies**
  - `sudo ufw default deny incoming`
  - `sudo ufw default allow outgoing`
  - Whitelist security approach
- **Allowing SSH**
  - IP-restricted SSH access
  - `sudo ufw allow from [IP] to any port 22`
  - Attack surface reduction
- **Enabling Firewall**
  - `sudo ufw enable`
  - Verifying rules
  - Numbered rule display

### Chapter 8: Defense-in-Depth Strategy
- **Multiple Security Layers:**
  1. Network Level: Firewall blocking unauthorized connections
  2. Access Level: Key-based SSH authentication
  3. Authorization Level: User privileges and sudo
  4. Data Level: Encrypted communications
- Comprehensive security implementation

### Chapter 9: User and Privilege Management
- **Creating Administrative Users**
  - `sudo adduser [username]`
  - Strong password policy
- **Adding to Sudo Group**
  - `sudo usermod -aG sudo [username]`
  - Group membership verification
  - Testing sudo access
- **Principle of Least Privilege**
  - Minimum necessary permissions
  - Regular vs. administrative users
  - Sudo for privilege escalation
  - Accountability and audit trails

### Chapter 10: Remote Administration
- **Remote Command Execution**
  - System information retrieval
  - Memory and disk information
  - Firewall status checking
  - Service status monitoring
- **Interactive SSH Sessions**
  - Workstation-to-server architecture
  - Remote administration workflow
  - Evidence requirements

### Chapter 11: Security Best Practices
- Configuration backup before changes
- Testing in separate session
- Strong passphrases for keys
- IP-restricted access
- Regular security audits
- Documentation of changes

### Chapter 12: Key Learnings
- Process monitoring and control
- SSH security implementation
- Firewall configuration
- User privilege management
- Defense-in-depth understanding
- Remote system administration

---

## Glossary of Key Terms

**API (Application Programming Interface):** Set of protocols and tools for building software applications

**Authentication:** Process of verifying user identity

**Authorization:** Determining what an authenticated user is permitted to do

**Context Switch:** Process of storing and restoring state when switching between processes

**Daemon:** Background process that runs continuously

**FIFO (Named Pipe):** Named file in filesystem for inter-process communication between unrelated processes

**IOPS (Input/Output Operations Per Second):** Number of I/O operations completed per second

**IPC (Inter-Process Communication):** Mechanisms for processes to communicate and synchronize

**Mutex:** Mutual exclusion lock ensuring only one thread accesses critical section

**PCB (Process Control Block):** Data structure containing process information

**POSIX:** Portable Operating System Interface standard

**Scheduler:** OS component that decides which process runs next

**Semaphore:** Signaling mechanism for controlling access to shared resources using counters

**SIGINT:** Signal sent by Ctrl+C for graceful process termination

**SIGKILL:** Uncatchable signal for forceful process termination

**SIGTERM:** Signal requesting graceful process termination (can be caught and handled)

**System Call:** Request for OS services from user programs

**UFW (Uncomplicated Firewall):** User-friendly firewall management tool for Linux

**Virtualization:** Technology allowing multiple OS to run on single physical machine

---

## Progress Tracker

- [x] Week 1: Linux Environment Setup and Basic Commands
- [x] Week 2: Command-Line Fundamentals
- [x] Week 3: Linux Distribution Comparison and Performance Monitoring
- [x] Week 4: System Planning and Distribution Selection
- [x] Week 5: Inter-Process Communication (IPC)
- [x] Week 7: Process Management and Initial Security Configuration

---

**Last Updated:** December 17, 2025
**Status:** Weeks 1-7 Complete (6 weeks documented)
