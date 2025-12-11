# Operating Systems Course Journal
## A Comprehensive Study Guide

**Course:** Operating Systems
**Academic Period:** October 2025
**Status:** Complete (Weeks 1-9 Complete)

---

## 📹 Linux Demonstration Video

Watch the complete Linux system demonstration showcasing the practical implementation of concepts covered in this course:

**[🎬 Watch on Vimeo: 8-Minutes Linux Demonstration](https://vimeo.com/1145579534)**

[![Linux Demonstration Video](https://i.vimeocdn.com/video/1993877652-8f8e8e8e8e8e8e8e8e8e8e8e8e8e8e8e8e8e8e8e8e8e8e8e8e8e8e8e8e8e8e8e8e8e8e_640.jpg)](https://vimeo.com/1145579534)

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

### [Part I: Foundations of Operating Systems](#part-i-foundations-of-operating-systems)
**Week 1** - [Operating Systems and Computing Sustainability](Main/Week-1-Journal.md)

### [Part II: Linux System Architecture](#part-ii-linux-system-architecture)
**Week 2** - [Linux Foundations and System Architecture](Main/Week-2-Journal.md)

### [Part III: Process Management and Scheduling](#part-iii-process-management-and-scheduling)
**Week 3** - [Process Management, Scheduling, and System Performance](Main/Week-3-Journal.md)

### [Part IV: Memory Management](#part-iv-memory-management)
**Week 4** - [Memory Management and Resource Allocation](Main/Week-4-Journal.md)

### [Part V: Inter-Process Communication](#part-v-inter-process-communication)
**Week 5** - [Inter-Process Communication (IPC)](Main/Week-5-Jornal.md)

### [Part VI: System Review and Integration](#part-vi-system-review-and-integration)
**Week 6** - [Operating Systems Comprehensive Review](Main/Week-6-Journal.md)

### [Part VII: Security Fundamentals](#part-vii-security-fundamentals)
**Week 7** - [Initial Security Configuration](Main/Week-7-Journal.md)

### [Part VIII: File Systems and Security Mechanisms](#part-viii-file-systems-and-security-mechanisms)
**Week 8** - [File System, Storage Performance, and Security Mechanisms](Main/Week-8-Jornal.md)

### [Part IX: Security Hardening](#part-ix-security-hardening)
**Week 9** - [System Security and Hardening](Main/Week-9-Jornal.md)

---

# Part I: Foundations of Operating Systems

## Week 1: [Operating Systems and Computing Sustainability](Main/Week-1-Journal.md)

**Focus:** Core concepts, architectural patterns, and environmental considerations in modern computing

### Chapter 1: Introduction to Operating Systems
- Definition and fundamental purpose of operating systems
- Core functions: Resource allocation, abstraction, protection, virtualization
- Historical evolution from batch systems to modern multi-tasking OS
- Significance in contemporary computing environments

### Chapter 2: Types of Operating Systems
- **Batch Operating Systems:** Sequential job processing
- **Time-Sharing Systems:** Multi-user resource sharing
- **Distributed Systems:** Coordinated independent computers
- **Real-Time Systems:** Guaranteed response times (Hard & Soft RTOS)
- **Network Operating Systems:** Networked resource management
- **Mobile Operating Systems:** Touch-optimized, power-efficient platforms

### Chapter 3: Operating System Modes
- **User Mode:** Restricted execution environment for applications
- **Kernel Mode:** Privileged execution with full hardware access
- Mode switching mechanisms and performance implications
- Protection rings in modern processors (Ring 0-3)

### Chapter 4: OS Architecture Patterns
- **Monolithic Architecture:** Single large kernel program
  - Advantages: High performance, efficient resource sharing
  - Disadvantages: Poor modularity, single point of failure
- **Microkernel Architecture:** Minimal kernel with user-space services
  - Advantages: Enhanced reliability, better security, improved modularity
  - Disadvantages: Performance overhead, IPC complexity
- **Hybrid/Layered Architecture:** Combined approach
- **Exokernel Architecture:** Application-specific OS abstractions
- **Unikernel Architecture:** Single-purpose compiled systems

### Chapter 5: Architecture Layers
- **Layer 0:** Hardware foundation
- **Layer 1:** Hardware Abstraction Layer (HAL)
- **Layer 2:** Kernel core (scheduler, interrupt handlers)
- **Layer 3:** Resource managers (memory, process, I/O, file system)
- **Layer 4:** System services and device drivers
- **Layer 5:** User interface (CLI, GUI, APIs)
- **Layer 6:** Application layer

### Chapter 6: System Calls
- Definition and programmatic interface to kernel services
- Categories of system calls:
  - Process control (`fork()`, `exec()`, `exit()`, `wait()`)
  - File management (`open()`, `read()`, `write()`, `close()`)
  - Device management (`ioctl()`)
  - Information maintenance (`getpid()`, `time()`, `sysinfo()`)
  - Communication (`pipe()`, `socket()`, `send()`, `recv()`)
  - Protection and security (`chmod()`, `chown()`, `setuid()`)
- System call invocation mechanism and performance considerations

### Chapter 7: Process Control
- Process definition and components
- Process vs. Program distinction
- Process states: New, Ready, Running, Waiting, Terminated, Suspended
- Process Control Block (PCB) structure and importance
- Process scheduling:
  - Scheduling queues (job, ready, device)
  - Scheduling algorithms (FCFS, SJF, Priority, Round Robin)
  - Long-term, short-term, and medium-term schedulers

### Chapter 8: Resource Management
- CPU scheduling and allocation
- Memory management fundamentals
- I/O device management
- Resource allocation strategies and policies

### Chapter 9: File Systems
- File system organization and structure
- File operations and access methods
- Directory structures and navigation
- File system implementation concepts

### Chapter 10: OS Evolution Timeline
- Historical development of operating systems
- Major milestones and technological breakthroughs
- Evolution of design philosophies

### Chapter 11: Contemporary OS Challenges
- Security and privacy concerns
- Scalability in distributed environments
- Power efficiency and thermal management
- Real-time performance requirements

### Chapter 12-19: Computing Sustainability
- **Manufacturing:** Environmental impact of hardware production
- **Operational Use:** Energy consumption patterns
- **Data Centre Impact:** Large-scale computing environmental effects
- **Energy Consumption Breakdown:** Analysis of power usage
- **Hardware Efficiency Strategies:** Optimization techniques
- **Performance vs Energy Efficiency:** Trade-off analysis
- **User Experience vs Resource Conservation:** Balancing priorities
- **Initial Cost vs Lifecycle Impact:** Long-term sustainability
- **Legacy Support vs Optimization:** Modernization challenges

---

# Part II: Linux System Architecture

## Week 2: [Linux Foundations and System Architecture](Main/Week-2-Journal.md)

**Focus:** Linux-specific implementations, command-line tools, and practical system administration

### Chapter 1: System Architecture and Linux Foundations
- Linux ecosystem overview
- Open-source development model
- POSIX compliance and standards

### Chapter 2: Operating System Design Principles
- Unix philosophy and design principles
- Modularity, simplicity, and composability
- Everything is a file paradigm

### Chapter 3: Command-Line Tools in Linux
- Essential CLI utilities and commands
- Text processing tools
- System administration commands
- Shell scripting fundamentals

### Chapter 4: Kernel Architecture
- Linux kernel structure and organization
- Kernel subsystems and their interactions
- Kernel development and compilation

### Chapter 5: Kernel and GNU/Linux
- GNU toolchain components
- Relationship between kernel and userspace
- GPL licensing and implications

### Chapter 6: Layered Design
- Linux architectural layers
- Abstraction levels in Linux
- Interface boundaries and APIs

### Chapter 7: Distribution Families
- **Debian-based:** Ubuntu, Linux Mint, Debian
- **Red Hat-based:** RHEL, CentOS, Fedora
- **Arch-based:** Arch Linux, Manjaro
- **SUSE-based:** openSUSE, SUSE Enterprise
- Distribution selection criteria

### Chapter 8: Process Management
- Process creation in Linux (`fork()`, `exec()`)
- Process hierarchy and relationships
- Process monitoring tools (`ps`, `top`, `htop`)

### Chapter 9: File System Navigation
- File system hierarchy standard (FHS)
- Directory structure and organization
- Navigation commands and techniques
- Path resolution (absolute vs. relative)

### Chapter 10: Boot Process
- Boot sequence overview
- Initialization stages
- Service startup and dependency management

### Chapter 11: Package Management
- **APT** (Debian/Ubuntu): `apt`, `apt-get`, `dpkg`
- **YUM/DNF** (Red Hat/Fedora): `yum`, `dnf`, `rpm`
- **Pacman** (Arch): `pacman`
- Package repositories and dependency resolution

### Chapter 12: System Information
- Hardware information commands (`lscpu`, `lshw`, `lsblk`)
- System monitoring tools (`uname`, `uptime`, `free`)
- Performance analysis utilities

### Chapter 13: Monolithic Kernel
- Linux monolithic kernel design
- Advantages in Linux context
- Loadable kernel modules (LKMs)

### Chapter 14: Microkernel
- Microkernel principles and examples
- Comparison with Linux approach
- Use cases and trade-offs

### Chapter 15: Hybrid Kernel
- Hybrid kernel characteristics
- Windows NT and macOS XNU examples
- Design philosophy comparison

### Chapter 16: Modularity Principle
- Kernel modularity in Linux
- Module loading and unloading
- Dynamic kernel configuration

### Chapter 17: BIOS/UEFI POST
- Power-On Self Test (POST) process
- BIOS vs. UEFI comparison
- Firmware initialization stages

### Chapter 18: Bootloader
- GRUB (Grand Unified Bootloader)
- Bootloader configuration
- Multi-boot systems

### Chapter 19: Kernel Loading
- Kernel image loading process
- Initial RAM disk (initrd/initramfs)
- Kernel initialization

---

# Part III: Process Management and Scheduling

## Week 3: [Process Management, Scheduling, and System Performance](Main/Week-3-Journal.md)

**Focus:** Advanced process concepts, scheduling algorithms, and performance optimization

### Chapter 1: Process Management & System Performance
- Process management strategies
- Performance implications of process design
- System resource optimization

### Chapter 2: Threads
- Thread concepts and implementation
- User-level vs. kernel-level threads
- Multi-threading models:
  - Many-to-One model
  - One-to-One model
  - Many-to-Many model
- Thread libraries (POSIX Pthreads, Java threads)

### Chapter 3: Concurrency Problems
- **Race Conditions:** Timing-dependent bugs
- **Deadlocks:** Circular resource waiting
- **Starvation:** Indefinite resource denial
- **Priority Inversion:** Low-priority process blocking high-priority
- Critical section problem

### Chapter 4: Problems with Race Condition Solutions
- Inadequate synchronization mechanisms
- Performance overhead of locking
- Complexity in concurrent programming
- Debugging challenges

### Chapter 5: Solving Race Conditions
- **Mutual Exclusion:** Only one process in critical section
- **Semaphores:** Signaling mechanisms
  - Binary semaphores
  - Counting semaphores
- **Mutexes:** Mutual exclusion locks
- **Monitors:** High-level synchronization construct
- **Condition Variables:** Thread coordination
- Peterson's algorithm and hardware solutions

### Chapter 6: Scheduling Algorithms
- Scheduling objectives and metrics
- Algorithm comparison and selection criteria
- Real-world scheduling implementations

### Chapter 7: Performance Monitoring
- System performance metrics
- Monitoring tools and utilities
- Performance bottleneck identification
- Profiling techniques

### Chapter 8: Process Fundamentals
- Detailed process anatomy
- Process address space layout
- Memory regions: text, data, BSS, heap, stack
- Process creation mechanics

### Chapter 9: Process Control Block (PCB)
- PCB structure and contents
- Context switching mechanism
- PCB management in different OS

### Chapter 10: Process Lifecycle and State Transitions
- Detailed state transition diagrams
- Event-driven state changes
- Scheduling queue interactions
- Process termination and cleanup

### Chapter 11: CPU Scheduling Concepts
- Preemptive vs. non-preemptive scheduling
- Scheduling criteria:
  - CPU utilization
  - Throughput
  - Turnaround time
  - Waiting time
  - Response time
- Dispatcher and context switch overhead

### Chapter 12: Scheduling Algorithms: FCFS and SJF
- **First-Come, First-Served (FCFS)**
  - Implementation simplicity
  - Convoy effect problem
  - Use cases
- **Shortest Job First (SJF)**
  - Optimal average waiting time
  - Prediction challenges
  - Preemptive variant (SRTF)

### Chapter 13: Scheduling Algorithms: Priority and Round Robin
- **Priority Scheduling**
  - Static vs. dynamic priorities
  - Starvation problem
  - Aging solution
- **Round Robin (RR)**
  - Time quantum selection
  - Context switching overhead
  - Fair scheduling guarantee

### Chapter 14: Multi-threading and Process Synchronization
- Benefits of multi-threading
- Thread synchronization primitives
- Synchronization challenges
- Best practices for concurrent programming

### Chapter 15: Performance Metrics and KPIs
- Key Performance Indicators (KPIs)
- Throughput and latency measurements
- Resource utilization metrics
- System benchmarking

### Chapter 16: Bottleneck Identification and Analysis
- Performance profiling techniques
- Identifying CPU, memory, I/O bottlenecks
- Analysis tools and methodologies
- Optimization strategies

---

# Part IV: Memory Management

## Week 4: [Memory Management and Resource Allocation](Main/Week-4-Journal.md)

**Focus:** Memory hierarchies, virtual memory, and containerization

### Chapter 1: Memory Management and Resource Allocation
- Memory management objectives
- Memory hierarchy (registers, cache, RAM, storage)
- Allocation strategies overview
- Memory protection mechanisms

### Chapter 2: Physical vs. Virtual Memory
- **Physical Memory:** Direct hardware addressing
- **Virtual Memory:** Abstraction layer benefits
  - Address space isolation
  - Memory overcommitment
  - Demand paging
- Address translation mechanism (MMU)
- Page tables and address mapping

### Chapter 3: Paging Mechanisms
- Paging concept and implementation
- Page size considerations
- Page table structure:
  - Single-level page tables
  - Multi-level page tables
  - Inverted page tables
- Translation Lookaside Buffer (TLB)
- Page replacement algorithms:
  - FIFO (First-In, First-Out)
  - LRU (Least Recently Used)
  - Optimal algorithm
  - Clock algorithm

### Chapter 4: Paging Advantages and Limitations
- **Advantages:**
  - Eliminates external fragmentation
  - Flexible memory allocation
  - Enables virtual memory
  - Simplifies memory allocation
- **Limitations:**
  - Internal fragmentation
  - Page table overhead
  - TLB misses
  - Performance considerations

### Chapter 5: Segmentation Mechanisms
- Segmentation concepts
- Segment table structure
- Logical address space organization
- Segmentation vs. paging comparison
- Segmentation with paging (hybrid approach)

### Chapter 6: Memory Allocation Strategies
- **Contiguous Allocation:**
  - Fixed partitioning
  - Dynamic partitioning
  - Fragmentation issues
- **Non-contiguous Allocation:**
  - Paging
  - Segmentation
- **Dynamic Allocation Algorithms:**
  - First Fit
  - Best Fit
  - Worst Fit
  - Buddy System
- Heap memory management
- Stack vs. heap allocation

### Chapter 7: Garbage Collection
- Automatic memory management
- Garbage collection algorithms:
  - Reference counting
  - Mark and Sweep
  - Copying collection
  - Generational collection
- GC performance impact
- Manual vs. automatic memory management trade-offs

### Chapter 8: Resource Isolation and Allocation
- Process isolation techniques
- Memory protection mechanisms
- Resource quotas and limits
- Access control and permissions

### Chapter 9: Containerisation Concepts
- Container technology overview
- Containers vs. virtual machines
- **Key Technologies:**
  - Namespaces (PID, network, mount, IPC, UTS, user)
  - Control groups (cgroups)
  - Union file systems
- Docker and container runtimes
- Container orchestration basics

### Chapter 10: Resource Limits and Quality of Service
- CPU shares and quotas
- Memory limits and OOM handling
- I/O bandwidth control
- Quality of Service (QoS) classes
- Resource prioritization strategies

### Chapter 11: Memory Monitoring Tools
- **Linux Tools:**
  - `free`: Memory usage summary
  - `vmstat`: Virtual memory statistics
  - `top`/`htop`: Real-time process monitoring
  - `ps`: Process status and memory usage
  - `/proc/meminfo`: Detailed memory information
- Memory leak detection
- Performance analysis and tuning

---

# Part V: Inter-Process Communication

## Week 5: [Inter-Process Communication (IPC)](Main/Week-5-Jornal.md)

**Focus:** IPC mechanisms, shared memory, message passing, pipes, signals, and synchronization

### Chapter 1: Introduction to IPC
- Definition of Inter-Process Communication
- Why processes need communication:
  - Information sharing
  - Computation speedup
  - Modularity and convenience
- Real-world examples: web browsers, shell pipelines, client-server applications

### Chapter 2: IPC Models Overview
- **Shared Memory Model:**
  - High speed with direct memory access
  - Higher complexity requiring synchronization
  - Best for performance-critical applications
- **Message Passing Model:**
  - Lower speed with kernel involvement
  - Lower complexity with built-in synchronization
  - Best for simplicity and distributed systems
- Key decision factors between models

### Chapter 3: Shared Memory Systems
- Concept and advantages: high speed, efficient for large data
- Challenges: complex synchronization, security risks
- Producer-consumer example demonstrating coordination
- Synchronization requirements for data integrity

### Chapter 4: Message Passing Systems
- Concept and system call interface (`send()`, `receive()`)
- **Direct Communication:** Explicit process naming
- **Indirect Communication:** Mailboxes/ports for loose coupling
- Client-server communication example

### Chapter 5: Pipes and Redirection in Unix
- Unix philosophy: small, modular programs
- **Pipe (|):** Connecting stdout to stdin
- **Redirection:** Output (>) and input (<) redirection
- How pipes create unidirectional communication channels

### Chapter 6: Pipes, FIFOs, and Sockets
- **Pipes (Anonymous):**
  - Unnamed, in-memory communication
  - Parent-child process relationships
  - Temporary existence
- **FIFOs (Named Pipes):**
  - Named files in filesystem
  - Unrelated process communication
  - Persistent until deleted
- **Sockets:**
  - Endpoints for local or network communication
  - Support TCP/UDP protocols
  - Bidirectional communication

### Chapter 7: Signals and Process Communication
- Definition: asynchronous notifications for events
- **Common Signals:**
  - SIGINT: Ctrl+C graceful termination
  - SIGKILL: Forceful termination (uncatchable)
  - SIGTERM: Termination request (catchable)
- Process management using signals
- `kill()` system call for sending signals

### Chapter 8: Synchronization Primitives
- **Semaphores:** Signaling mechanisms for resource control
- **Mutexes:** Mutual exclusion for exclusive access
- **Monitors:** High-level constructs encapsulating shared data
- Importance: prevent race conditions, ensure data consistency

### Chapter 9: IPC in Practice
- **Real-world Applications:**
  - Databases: shared memory for cache management
  - Web servers: multiple processes handling requests
  - OS components: kernel and daemon communication
  - Microservices: network sockets for distributed communication
- **Performance Considerations:**
  - Kernel involvement overhead
  - Data amount and transfer efficiency
  - Communication frequency impact
  - Process location (local vs. network)

### Chapter 10: Laboratory Exercises
- Task 1.1: Pipes and redirection
  - Standard streams and file redirection
  - Using pipes for command chaining
  - Complex pipeline construction
- Task 1.2: Named pipes (FIFOs)
  - Creating and using FIFOs
  - Producer/consumer pattern implementation
- Task 1.3: Process signals
  - Signal operations and handling
  - Custom signal handlers in bash
- Task 1.4: File-based IPC
  - Producer/consumer scripts
  - Lockfile synchronization mechanism

---

# Part VI: System Review and Integration

## Week 6: [Operating Systems Comprehensive Review](Main/Week-6-Journal.md)

**Focus:** Integration of OS fundamentals, CPU scheduling, process synchronization, memory management, and IPC

### Chapter 1: Operating System Fundamentals
- **Primary Functions:**
  - Process management
  - Memory management
  - File system management
  - I/O device management
- Operating system architectures review

### Chapter 2: Operating System Architectures
- **Layered Architecture:** Hierarchical organization
- **Monolithic Kernel:**
  - All services in kernel space
  - Better performance, less modular
  - Examples: Traditional Linux, Unix
- **Microkernel Architecture:**
  - Minimal kernel, services in user space
  - Better security/isolation, potential performance overhead
  - Examples: Minix, QNX

### Chapter 3: Boot Process
- **Sequence:**
  1. BIOS/UEFI: Hardware initialization, POST
  2. Bootloader: Load OS kernel (GRUB, LILO)
  3. Kernel: Initialize system, mount filesystem
  4. Init System: Start services (PID 1)
- GNU/Linux relationship

### Chapter 4: CPU Scheduling Algorithms
- **First-Come-First-Serve (FCFS):**
  - Non-preemptive, simple
  - Convoy effect disadvantage
- **Shortest Job First (SJF):**
  - Minimizes average waiting time
  - Starvation risk for longer processes
  - Preemptive variant: SRTF
- **Round Robin (RR):**
  - Time quantum allocation
  - Fair, good for time-sharing
- **Priority Scheduling:**
  - Priority-based execution
  - Aging prevents starvation
- **Multi-Level Feedback Queue (MLFQ):**
  - Multiple priority queues
  - Automatic I/O-bound vs CPU-bound identification

### Chapter 5: Process Synchronization
- **Race Conditions:**
  - Non-deterministic execution ordering
  - Banking application example
- **Synchronization Mechanisms:**
  - Semaphores: Counter-based access control
  - Mutex: Binary lock for mutual exclusion
  - Monitor: High-level synchronization construct
  - Spinlock: Busy-waiting lock
- **Critical Section:** Code requiring atomic execution
- Solution requirements: mutual exclusion, progress, bounded waiting

### Chapter 6: Memory Management
- **Memory Allocation Algorithms:**
  - First-Fit: First adequate hole
  - Best-Fit: Smallest adequate hole (minimizes waste)
  - Worst-Fit: Largest hole (leaves larger fragments)
  - Next-Fit: Continues from last allocation
- **Fragmentation:**
  - External: Scattered free memory
  - Internal: Wasted space in allocations
- **Paging:** Fixed-size pages, eliminates external fragmentation
- **Segmentation:**
  - Variable-size segments
  - Base and limit registers
  - Address translation and validation

### Chapter 7: Inter-Process Communication (IPC)
- **Pipes:** Unidirectional parent-child communication
- **FIFOs:** Named pipes for unrelated processes
- **Shared Memory:**
  - Fastest IPC (zero-copy)
  - Requires explicit synchronization
  - Best for large data transfers
- **Message Queues:**
  - Automatic synchronization
  - Kernel manages queue
  - Better for small messages
- **Sockets:**
  - Network communication capability
  - TCP: Reliable, connection-oriented
  - UDP: Fast, unreliable, connectionless

### Chapter 8: Signals and Process Management
- **Common Signals:**
  - SIGINT (2): Ctrl+C interrupt
  - SIGTERM (15): Graceful termination request
  - SIGKILL (9): Force kill (uncatchable)
  - SIGCHLD: Child process termination notification
  - SIGSTOP: Pause execution
- **Graceful Shutdown:** Web server signal flow example
- Zombie process prevention with `wait()`

### Chapter 9: System Performance Analysis
- **Bottleneck Identification:**
  - Disk I/O bottleneck symptoms and solutions
  - CPU scheduling bottleneck resolution
- **Workload Optimization:**
  - CPU-bound vs I/O-bound balancing
  - MLFQ automatic optimization

### Chapter 10: Key Concepts Summary
- Process states and lifecycle
- Context switching overhead
- Zombie processes and prevention
- Critical section problem requirements

### Chapter 11: Practical Applications
- IPC mechanism selection criteria
- Memory allocation strategy selection
- Scheduling algorithm selection by workload

### Chapter 12: Common Pitfalls and Best Practices
- Synchronization best practices
- Signal handling guidelines
- Memory management considerations
- IPC selection criteria

---

# Part VII: Security Fundamentals

## Week 7: [Initial Security Configuration](Main/Week-7-Journal.md)

**Focus:** OS security fundamentals, access control models, intrusion detection, and practical security configuration

### Chapter 1: OS Security Fundamentals - The AAA Framework
- **Authentication:** Verifying user identity ("Who are you?")
  - Methods: passwords, biometrics, digital certificates
- **Authorization:** Determining permissions ("What can you do?")
  - Defining access to resources and operations
- **Access Control:** Enforcing authorization policies
  - Actively grants or denies requests

### Chapter 2: Importance of Initial Security Setup
- **Common Vulnerabilities:**
  - Default passwords: Easy entry points
  - Unnecessary services: Expanded attack surface
  - Improper permissions: Unauthorized file access
- **Attack Vectors:**
  - Network exploits via default credentials
  - Local privilege escalation through misconfigurations

### Chapter 3: OS-Level Vulnerabilities & Impact
- **Common Vulnerabilities:**
  - Buffer overflows: Memory corruption, crashes
  - Race conditions: Timing-based privilege escalation
  - Improper input validation: Injection attacks
  - Use-after-free: Memory corruption vulnerabilities
- **System Impact:**
  - System integrity: Data modification, backdoors
  - Confidentiality: Data exposure, identity theft

### Chapter 4: Security Models: DAC, MAC, RBAC
- **Discretionary Access Control (DAC):**
  - Owner-centric permissions
  - High flexibility, lower security
  - Examples: Unix/Linux file permissions
- **Mandatory Access Control (MAC):**
  - System-enforced security levels
  - Low flexibility, high security
  - Examples: SELinux, AppArmor
- **Role-Based Access Control (RBAC):**
  - Role-privilege mapping
  - Scalable for large organizations
  - Examples: Enterprise systems, cloud platforms

### Chapter 5: Mandatory Access Control (MAC) Concepts
- **Reference Monitor:**
  - Kernel component mediating all access
  - Tamper-proof, always invoked
  - Compares security labels for decisions
- **Security Labels:**
  - System-defined classification
  - Hierarchical levels (Top Secret to Unclassified)
  - Cannot be changed by users
- **Implementations:**
  - SELinux: Policy-driven, type enforcement
  - AppArmor: Path-based, profile confinement

### Chapter 6: DAC vs. MAC Comparison
- Control method differences
- Flexibility and security trade-offs
- Use case recommendations

### Chapter 7: Introduction to Intrusion Detection Systems
- **Host-based IDS (HIDS):**
  - Monitors specific host activities
  - Detects internal attacks, file access
  - Resource intensive on host
- **Network-based IDS (NIDS):**
  - Monitors network traffic
  - Detects port scans, DoS attacks
  - Cannot see encrypted traffic

### Chapter 8: IDS Components & Workflow
- **Detection Techniques:**
  - Signature-based: Known attack patterns
  - Anomaly-based: Deviation from normal behavior
- **Workflow:**
  1. Data collection
  2. Analysis engine processing
  3. Detection and threat assessment
  4. Response: alert or continue monitoring

### Chapter 9: Bash Scripting for System Administration
- **Automation Tasks:**
  - User auditing and management
  - Log file analysis for security events
  - File permission control enforcement
- **Useful Commands:**
  - chmod: Change file permissions
  - chown: Change file ownership
  - grep: Search text patterns in logs

### Chapter 10: Operating System Modes Review
- **User Mode:**
  - Limited privileges
  - Application execution
  - Isolated from other processes
- **Kernel Mode:**
  - Full system access
  - OS core functions
  - Device driver execution
- **Mode Transition:** System calls, interrupts, exceptions

### Chapter 11: Laboratory Activities
- **Part 1: Process Fundamentals**
  - Exploring process states with ps, top, htop
  - Process relationships and control
  - Process lifecycle understanding
- **Part 2: SSH Key-Based Authentication**
  - Generating ed25519 SSH keys
  - Copying keys to server
  - Hardening SSH configuration
- **Part 3: Firewall and User Management**
  - UFW firewall configuration
  - User privilege management
  - Remote administration practices

### Chapter 12: Self-Assessment & Reflection
- Authentication vs. Authorization distinction
- Common vulnerabilities mitigation
- DAC vs. MAC key differences

---

# Part VIII: File Systems and Security Mechanisms

## Week 8: [File System, Storage Performance, and Security Mechanisms](Main/Week-8-Jornal.md)

**Focus:** File system architecture, storage performance optimization, and advanced security implementation

### Chapter 1: Introduction to File Systems
- **File System Definition:** Method and data structure for storage control
- **Key Roles:**
  - Data management and organization
  - Abstraction layer hiding hardware details
  - Data integrity through journaling
  - Access control and security
- I/O performance importance

### Chapter 2: File System Concepts
- **Core Components:**
  - Files: Named data collections
  - Directories: Hierarchical organization
  - Metadata: Size, owner, permissions, timestamps
- **Attributes & Naming:**
  - File attributes: read-only, hidden, system, archive
  - Naming conventions: length restrictions, forbidden characters, case sensitivity

### Chapter 3: File System Structure
- **Layered Architecture:**
  1. Application Interface: System calls
  2. Logical File System: Organization and security
  3. File-Organization Module: Block mapping
  4. Basic File System: I/O scheduling
  5. I/O Control: Device drivers
  6. Devices: Physical storage
- **Implementations:**
  - UFS: Inodes, case-sensitive
  - NTFS: Advanced security, journaling, compression

### Chapter 4: File Allocation and Access Methods
- **Allocation Methods:**
  - Contiguous: Sequential blocks, fast access, fragmentation
  - Linked: No fragmentation, slow direct access
  - Indexed: Fast access, no fragmentation, overhead
- **Access Methods:**
  - Sequential: Order-based reading
  - Direct (Random): Arbitrary position access

### Chapter 5: Directory Implementation
- **Structures:**
  - Single-Level: Simple, naming conflicts
  - Two-Level: User separation, limited organization
  - Tree-Structured: Hierarchical, flexible, no conflicts

### Chapter 6: Storage Devices and Performance
- **HDD vs. SSD Comparison:**
  - Mechanism: Mechanical vs. flash memory
  - Seek time: ms vs. µs (100x faster)
  - Transfer rate: 50-200 MB/s vs. 500-7000 MB/s
  - Random I/O: Poor vs. excellent
- **Performance Metrics:**
  - Latency: Request to transfer delay
  - Throughput: Data per second
  - IOPS: Operations per second

### Chapter 7: Storage Performance Monitoring
- **Key Metrics:** Latency, throughput, IOPS, utilization, queue depth
- **Tools:**
  - Linux: iostat, vmstat
  - Windows: Performance Monitor

### Chapter 8: I/O Performance Analysis
- **Techniques:**
  - Bottleneck identification
  - Workload characterization (read/write, random/sequential)
- **Optimization:**
  - Faster storage media (SSD, NVMe)
  - RAID configurations
  - Load balancing across devices
  - Application improvements
  - Caching and buffering
  - File system tuning

### Chapter 9: Caching and Buffering
- **Caching:**
  - Stores frequently accessed data in RAM
  - Cache hit vs. cache miss
  - Based on locality principles
- **Buffering:**
  - Temporary data storage during transfers
  - Smoothes transfer rate differences
  - Reduces physical I/O operations
- **Modern OS Examples:**
  - Linux: Unified buffer cache/page cache
  - Windows: Memory-mapped files, lazy write

### Chapter 10: Resource Management Context
- **CPU Impact:** Delays I/O processing, slow metadata updates
- **Memory Impact:** Page swapping increases I/O, limited cache
- **I/O Management:** Driver quality, controller capabilities, scheduling
- Holistic approach required for optimization

### Chapter 11: Mandatory Access Control Implementation
- **Access Control Systems:**
  - DAC: Traditional file permissions
  - MAC: System-wide security policy
- **AppArmor:**
  - Profile-based security
  - Enforce and complain modes
  - Status reporting scripts
- **SELinux:**
  - Label-based security
  - Security contexts
  - Policy enforcement

### Chapter 12: Intrusion Detection with fail2ban
- **Function:** Monitors logs, automatically bans malicious IPs
- **Configuration:**
  - maxretry: Failed attempts before ban
  - bantime: Ban duration
  - findtime: Time window for counting failures
- **Monitoring:** Active jails, banned IPs, log analysis

### Chapter 13: Automatic Security Updates
- **Implementation:** unattended-upgrades package
- **Trade-offs:**
  - Pro: Automatic security patches
  - Con: Potential compatibility issues
  - Recommendation: Enable for security, test major updates

### Chapter 14: Security Verification and Monitoring
- **Security Baseline Script:**
  - SSH configuration verification
  - Firewall status check
  - Intrusion detection monitoring
  - MAC system verification
  - User privilege audit
- **Remote Monitoring Script:**
  - System information collection
  - Resource utilization tracking
  - Network monitoring
  - Security event reporting

---

# Part IX: Security Hardening

## Week 9: [System Security and Hardening](Main/Week-9-Jornal.md)

**Focus:** Security auditing, network assessment, hardening strategies, and best practices

### Chapter 1: Introduction to Security Auditing
- **Definition:** Systematic evaluation of security infrastructure
- **Functions:**
  - Assess controls and compliance
  - Detect breaches
  - Recommend improvements
- **Comparison:**
  - Security Audit: Comprehensive evaluation
  - Vulnerability Assessment: Identifying weaknesses
  - Penetration Testing: Exploiting vulnerabilities

### Chapter 2: Network Security Assessment Principles
- **Methods:**
  - Penetration testing: Simulated attacks
  - Vulnerability scanning: Automated flaw detection
- **Tools:**
  - Nmap: Network discovery and auditing
  - Nessus: Vulnerability scanning
  - Wireshark: Packet analysis
  - Metasploit: Exploitation framework
- **Workflow:**
  1. Reconnaissance: Information gathering
  2. Enumeration: Identifying hosts, ports, services
  3. Analysis: Evaluating vulnerabilities

### Chapter 3: Security Auditing with Automated Tools
- **Key Tools:**
  - Lynis: Comprehensive security scanner
  - OpenSCAP: SCAP implementation for compliance
  - chkrootkit: Rootkit detection
- **Audit Workflow:** Scan → Report → Fix → Re-scan

### Chapter 4: Security Hardening Strategies
- **Core Strategies:**
  1. Disable unused services
  2. Keep systems updated
  3. Implement mandatory access control
  4. Enforce strong authentication
- **Principles:**
  - Least Privilege: Minimum necessary permissions
  - Comprehensive Patch Management: Systematic updates

### Chapter 5: Linux Security Hardening Best Practices
- **Key Practices:**
  1. File Permissions: Proper access control
  2. Advanced Attributes (chattr): Immutable files
  3. SSH Hardening: Secure remote access
- **Philosophy:** "Security is a process, not a product"

### Chapter 6: File Permissions and Advanced Attributes
- **Linux Permissions:**
  - Categories: User, Group, Others
  - Types: Read (4), Write (2), Execute (1)
  - Numeric notation examples
- **Advanced Attributes:**
  - Immutable (+i): Prevents modification/deletion
  - Even root cannot modify without removing attribute

### Chapter 7: User and Access Management
- **Secure Policies:**
  - Password aging with chage
  - PAM configuration for authentication
  - Restrictive sudo policy
  - Least privilege principle
- **Access Control:**
  - Restrict root SSH access
  - Review sudo logs for auditing
  - Role-based privilege assignment

### Chapter 8: SSH Security Configuration
- **Three Pillars:**
  1. Disable root login: Prevent direct superuser access
  2. Key-based authentication: Cryptographically secure
  3. Change default port: Reduce automated attacks
- **Best Practice:** Always restart sshd after configuration changes

### Chapter 9: Firewall Configuration and Network Security
- **Firewall Fundamentals:**
  - Monitors and controls traffic
  - Barrier between trusted/untrusted networks
- **Tools:**
  - iptables: Flexible, complex syntax
  - firewalld: Dynamic management with zones
  - ufw: User-friendly frontend
- **Chains:**
  - INPUT: Incoming traffic control
  - OUTPUT: Outgoing traffic control
- **Intrusion Detection:**
  - fail2ban: Log-based IP blocking
  - Snort: Network intrusion detection

### Chapter 10: Monitoring and Incident Response
- **Continuous Monitoring:**
  - Log analysis: journalctl, syslog, auditd
  - Real-time alerting: OSSEC, Wazuh
- **Incident Response Process:**
  1. Detect: Identify incident
  2. Contain: Limit impact
  3. Eradicate: Remove cause
  4. Recover: Restore service

### Chapter 11: Integrating Security into System Design
- **Secure Architecture:**
  - Secure boot: Trusted software verification
  - Kernel module integrity: Tamper prevention
- **Automation & Consistency:**
  - Configuration management: Ansible, Puppet
  - Automated backups: Data protection
  - Automated patching: Timely updates
- **Layered Security Example:**
  - Application → Web Server → Firewall → Hardened OS → Hardware

### Chapter 12: Practical Troubleshooting Scenario
- **Scenario:** New sysadmin first-day assessment
- **Issues Found:**
  - Root login enabled with brute-force attack
  - World-readable sensitive files
  - Shared administrative account
- **Solutions:**
  - Disable root login, enable key authentication, configure fail2ban
  - Correct permissions, use immutable attributes
  - Create individual accounts with restrictive sudo

### Chapter 13: Assessment - Advanced Security and Monitoring
- **Deliverables:**
  1. Implement MAC (SELinux/AppArmor)
  2. Configure automatic security updates
  3. Configure fail2ban intrusion detection
  4. Create security baseline verification script
  5. Create remote monitoring script
- **Requirements:**
  - Detailed documentation
  - Line-by-line script comments
  - Video demonstration
  - Error handling and clear output

---

## Glossary of Key Terms

**API (Application Programming Interface):** Set of protocols and tools for building software applications

**AppArmor:** Path-based Mandatory Access Control system using application profiles

**Authentication:** Process of verifying user identity

**Authorization:** Determining what an authenticated user is permitted to do

**Context Switch:** Process of storing and restoring state when switching between processes

**DAC (Discretionary Access Control):** Owner-centric access control where resource owners define permissions

**Daemon:** Background process that runs continuously

**fail2ban:** Intrusion prevention software that monitors logs and bans malicious IP addresses

**FIFO (Named Pipe):** Named file in filesystem for inter-process communication between unrelated processes

**IOPS (Input/Output Operations Per Second):** Number of I/O operations completed per second

**IPC (Inter-Process Communication):** Mechanisms for processes to communicate and synchronize

**MAC (Mandatory Access Control):** System-enforced access control based on security labels and policies

**MLFQ (Multi-Level Feedback Queue):** Scheduling algorithm with multiple priority queues that automatically categorizes processes

**Mutex:** Mutual exclusion lock ensuring only one thread accesses critical section

**PCB (Process Control Block):** Data structure containing process information

**POSIX:** Portable Operating System Interface standard

**RBAC (Role-Based Access Control):** Access control model where permissions are assigned to roles

**Scheduler:** OS component that decides which process runs next

**SELinux (Security-Enhanced Linux):** Label-based Mandatory Access Control system with policy enforcement

**Semaphore:** Signaling mechanism for controlling access to shared resources using counters

**SIGINT:** Signal sent by Ctrl+C for graceful process termination

**SIGKILL:** Uncatchable signal for forceful process termination

**SIGTERM:** Signal requesting graceful process termination (can be caught and handled)

**System Call:** Request for OS services from user programs

**TLB (Translation Lookaside Buffer):** Cache for virtual-to-physical address translations

---

## Additional Resources

### Recommended Reading
- "Operating System Concepts" by Silberschatz, Galvin, and Gagne
- "Modern Operating Systems" by Andrew S. Tanenbaum
- "The Linux Programming Interface" by Michael Kerrisk

### Online Resources
- Linux kernel documentation
- GNU/Linux man pages
- Operating Systems course materials

---

## Progress Tracker

- [x] Week 1: Operating Systems Foundations
- [x] Week 2: Linux System Architecture
- [x] Week 3: Process Management and Scheduling
- [x] Week 4: Memory Management
- [x] Week 5: Inter-Process Communication
- [x] Week 6: Operating Systems Comprehensive Review
- [x] Week 7: Initial Security Configuration
- [x] Week 8: File System, Storage Performance, and Security Mechanisms
- [x] Week 9: System Security and Hardening

---

**Last Updated:** November 27, 2025
**Status:** 100% Complete (9/9 weeks)
