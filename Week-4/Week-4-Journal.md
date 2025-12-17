# Operating Systems: System Planning and Distribution Selection Journal

**Course:** Operating Systems
**Week:** 1
**Assessment:** Phase 1 - System Planning and Distribution Selection
**Student:** [Your Name]
**Date:** [Current Date]

---

## Table of Contents
1. [Introduction](#introduction)
2. [System Architecture Diagram](#1-system-architecture-diagram)
3. [Distribution Selection Justification](#2-distribution-selection-justification)
4. [Workstation Configuration Decision](#3-workstation-configuration-decision)
5. [Network Configuration Documentation](#4-network-configuration-documentation)
6. [System Specifications Documentation](#5-system-specifications-documentation)
7. [Conclusion](#conclusion)
8. [References](#references)

---

## Introduction

This journal documents Phase 1 of the Operating Systems assessment, focusing on system planning and distribution selection. The goal is to plan an operating system deployment, justify technical decisions, and document the configuration of both server and workstation systems in a virtualized environment.

This phase establishes the foundation for subsequent system administration tasks by carefully selecting appropriate distributions, designing the network architecture, and documenting baseline system specifications.

---

## 1. System Architecture Diagram

### Overview

The system architecture consists of two primary components deployed in a virtualized environment using VirtualBox:

1. **Linux Server** - Handles backend services and system administration tasks
2. **Linux Workstation** - Provides user interface and client-side functionality

### Network Topology

```
┌─────────────────────────────────────────────────────────────┐
│                      Host Machine                            │
│                  (Windows/macOS/Linux)                       │
│                                                              │
│  ┌────────────────────────────────────────────────────┐    │
│  │              VirtualBox Environment                 │    │
│  │                                                     │    │
│  │  ┌──────────────────┐      ┌──────────────────┐  │    │
│  │  │  Linux Server    │      │ Linux Workstation│  │    │
│  │  │                  │      │                  │  │    │
│  │  │  - Ubuntu Server │      │  - Ubuntu Desktop│  │    │
│  │  │  - IP: 10.0.2.15 │◄────►│  - IP: 10.0.2.16 │  │    │
│  │  │  - 2GB RAM       │      │  - 4GB RAM       │  │    │
│  │  │  - 2 vCPUs       │      │  - 2 vCPUs       │  │    │
│  │  │  - 20GB Storage  │      │  - 25GB Storage  │  │    │
│  │  └────────┬─────────┘      └────────┬─────────┘  │    │
│  │           │                         │             │    │
│  │           └─────────┬───────────────┘             │    │
│  │                     │                             │    │
│  │         ┌───────────▼──────────────┐              │    │
│  │         │   NAT Network/Bridge     │              │    │
│  │         │   (VirtualBox Network)   │              │    │
│  │         └───────────┬──────────────┘              │    │
│  │                     │                             │    │
│  └─────────────────────┼─────────────────────────────┘    │
│                        │                                   │
└────────────────────────┼───────────────────────────────────┘
                         │
                         ▼
                   Internet/LAN
```

### System Components

#### Linux Server
- **Purpose:** Backend services, system administration, learning server management
- **Operating System:** Ubuntu Server 22.04 LTS (or alternative)
- **Resources:**
  - CPU: 2 virtual cores
  - RAM: 2GB
  - Storage: 20GB
  - Network: NAT or Bridged Adapter
- **Services:** SSH, system monitoring, potential web services

#### Linux Workstation
- **Purpose:** User interface, development environment, client operations
- **Operating System:** Ubuntu Desktop 22.04 LTS (or alternative)
- **Resources:**
  - CPU: 2 virtual cores
  - RAM: 4GB (higher for GUI requirements)
  - Storage: 25GB
  - Network: NAT or Bridged Adapter
- **Features:** GUI desktop environment, development tools

### Network Design Rationale

The architecture uses VirtualBox's networking capabilities to create isolated yet connected virtual machines. This design allows:

1. **Isolation:** Each VM operates independently with its own resources
2. **Communication:** Both systems can communicate with each other and the host
3. **Internet Access:** NAT provides outbound connectivity for updates and packages
4. **Security:** Isolated from production networks for learning purposes
5. **Flexibility:** Easy to modify, snapshot, and restore configurations

---

## 2. Distribution Selection Justification

### Chosen Distribution: Ubuntu Server 22.04 LTS

#### Selection Criteria

When selecting a server distribution, several factors were considered:

1. **Stability and Support**
2. **Community and Documentation**
3. **Package Management**
4. **Hardware Compatibility**
5. **Learning Resources**
6. **Industry Relevance**
7. **Long-term Support**

### Distribution Comparison

#### Ubuntu Server 22.04 LTS

**Advantages:**
- **Long-Term Support:** 5 years of security updates and maintenance (until 2027)
- **Extensive Documentation:** Comprehensive official documentation and community resources
- **Large Community:** Vast user base providing support and solutions
- **Package Availability:** APT package manager with extensive repositories
- **Enterprise-Ready:** Used in production environments worldwide
- **Cloud Integration:** Excellent support for cloud platforms (AWS, Azure, GCP)
- **Regular Updates:** Predictable release cycle with timely security patches
- **User-Friendly:** Easier learning curve for beginners

**Disadvantages:**
- **Resource Usage:** Slightly higher resource consumption than minimal distributions
- **Bloat Perception:** Some consider it bloated compared to minimal distros
- **Corporate Backing:** Some users prefer community-driven distributions

**Use Case Suitability:** Excellent for learning, development, and production servers requiring stability and support.

#### Alternative 1: CentOS Stream / Rocky Linux

**Advantages:**
- **Enterprise Standard:** Based on RHEL, widely used in enterprise environments
- **SELinux Integration:** Enhanced security out of the box
- **YUM/DNF Package Manager:** Robust package management
- **Stability:** Conservative approach to updates
- **Red Hat Ecosystem:** Access to Red Hat documentation and tools

**Disadvantages:**
- **CentOS Changes:** CentOS Stream is now upstream of RHEL (less stable)
- **Smaller Community:** Less community support than Ubuntu
- **Steeper Learning Curve:** More complex for beginners
- **Package Availability:** Fewer packages in default repositories

**Comparison:** More suitable for enterprise RHEL environments, but Ubuntu offers better learning resources.

#### Alternative 2: Debian 11 (Bullseye)

**Advantages:**
- **Rock-Solid Stability:** Extremely stable and reliable
- **Community-Driven:** No corporate control
- **Universal Operating System:** Supports many architectures
- **Minimal Base:** Lighter resource footprint
- **APT Package Manager:** Same package management as Ubuntu

**Disadvantages:**
- **Older Packages:** Prioritizes stability over cutting-edge features
- **Less Frequent Updates:** Longer release cycles
- **Less User-Friendly:** More technical, fewer conveniences
- **Smaller Corporate Adoption:** Less common in enterprise

**Comparison:** More stable but less user-friendly than Ubuntu, better for advanced users.

#### Alternative 3: Arch Linux

**Advantages:**
- **Rolling Release:** Always up-to-date packages
- **Minimalist Philosophy:** Install only what you need
- **AUR (Arch User Repository):** Massive package availability
- **Cutting-Edge:** Latest software versions
- **Learning Opportunity:** Deep understanding through manual configuration

**Disadvantages:**
- **No Stability Guarantee:** Rolling releases can break
- **Manual Configuration:** Requires significant setup time
- **Not Production-Ready:** Unsuitable for critical servers
- **No LTS:** No long-term support model
- **Time-Intensive:** Requires constant maintenance

**Comparison:** Excellent for learning Linux internals but impractical for stable server deployments.

### Final Justification

**Ubuntu Server 22.04 LTS** was selected because it provides:

1. **Optimal Learning Environment:** Extensive documentation and community support facilitate learning
2. **Industry Relevance:** Skills are directly transferable to professional environments
3. **Stability:** LTS ensures a stable platform for coursework without unexpected breakage
4. **Time Efficiency:** Less time troubleshooting, more time learning core concepts
5. **Resource Balance:** Reasonable resource requirements for virtualization
6. **Package Ecosystem:** Wide software availability for various exercises and projects

For an educational context where the focus is on learning operating system concepts rather than distribution-specific configuration, Ubuntu Server offers the best balance of usability, stability, and industry relevance.

---

## 3. Workstation Configuration Decision

### Chosen Option: Ubuntu Desktop 22.04 LTS

#### Workstation Options Considered

Three primary approaches were evaluated for the workstation configuration:

1. **Full Desktop Environment (Ubuntu Desktop)**
2. **Minimal GUI Installation (Server + Lightweight DE)**
3. **CLI-Only Workstation (No GUI)**

### Option 1: Ubuntu Desktop 22.04 LTS (SELECTED)

**Configuration:**
- Full GNOME desktop environment
- Pre-installed productivity tools
- Graphical package managers
- Native VirtualBox integration
- 4GB RAM allocation
- 25GB disk space

**Advantages:**
- **User-Friendly:** Familiar desktop interface reduces learning curve
- **Productivity:** GUI tools speed up certain tasks (file management, browser, development)
- **Visualization:** Better for understanding system monitoring tools with graphical output
- **Multitasking:** Easy window management and application switching
- **Development-Ready:** Pre-configured development environment with GUI IDEs
- **Documentation:** Screenshots and visual aids easier to create for assignments

**Disadvantages:**
- **Resource Intensive:** Requires more RAM and CPU than CLI alternatives
- **Overhead:** Desktop environment consumes resources even when unused
- **Complexity:** More components that could potentially malfunction
- **Slower Boot:** GUI initialization increases boot time

**Justification:** For coursework involving documentation, screenshots, and learning both GUI and CLI tools, a full desktop environment provides the best balance of functionality and ease of use.

### Option 2: Server + Lightweight Desktop Environment

**Configuration:**
- Ubuntu Server base
- Lightweight DE (XFCE, LXQt, or i3)
- Manual package installation
- Minimal pre-installed software
- 2-3GB RAM allocation

**Advantages:**
- **Resource Efficient:** Uses significantly less RAM than full desktop
- **Customization:** Build exactly what you need
- **Learning:** Deeper understanding through manual configuration
- **Performance:** Faster and more responsive

**Disadvantages:**
- **Setup Time:** Requires manual installation and configuration
- **Missing Features:** May lack some convenient tools and integrations
- **Compatibility:** Some software may not work perfectly with lightweight DEs
- **Distraction:** Troubleshooting DE issues detracts from learning OS concepts

**Comparison:** More efficient but requires significant setup time better spent on course content.

### Option 3: CLI-Only Workstation

**Configuration:**
- Ubuntu Server without GUI
- Terminal-only interface
- CLI-based tools exclusively
- 1-2GB RAM allocation

**Advantages:**
- **Minimal Resources:** Lowest resource consumption
- **CLI Mastery:** Forces proficiency with command-line tools
- **Server-Like:** More realistic server environment experience
- **Fast:** No GUI overhead

**Disadvantages:**
- **Steep Learning Curve:** Everything through terminal challenging for beginners
- **Limited Functionality:** No web browser, graphical tools, or easy multitasking
- **Documentation Difficulty:** Hard to create visual documentation
- **Development Limitations:** No graphical IDE or development tools

**Comparison:** While valuable for advanced Linux learning, it hinders productivity for coursework requiring documentation and varied tools.

### Decision Rationale

**Ubuntu Desktop 22.04 LTS** was selected for the workstation because:

1. **Course Requirements:** Assignments require screenshots, documentation, and varied tools
2. **Learning Efficiency:** Focus on OS concepts, not desktop environment configuration
3. **Practical Balance:** Learn both GUI and CLI while maintaining productivity
4. **Industry Reality:** Most administrators use both GUI and CLI tools
5. **Time Management:** Reduces setup and troubleshooting time
6. **Versatility:** Supports all course activities without limitations

The decision prioritizes learning operating system concepts over minimalism. As proficiency increases, transitioning to lighter-weight configurations becomes more practical.

---

## 4. Network Configuration Documentation

### VirtualBox Network Configuration

#### Network Adapter Type: NAT Network (Primary Configuration)

**Configuration Details:**

**Server VM Network Settings:**
- Adapter 1: NAT Network
- Network Name: NatNetwork (or custom name)
- Port Forwarding: SSH (Host: 2222 → Guest: 22)
- MAC Address: Auto-generated
- Cable Connected: Yes

**Workstation VM Network Settings:**
- Adapter 1: NAT Network
- Network Name: NatNetwork (same as server)
- MAC Address: Auto-generated
- Cable Connected: Yes

### Network Configuration Options Comparison

#### Option 1: NAT Network (SELECTED)

**Characteristics:**
- VMs can communicate with each other
- VMs can access the internet
- Host can access VMs via port forwarding
- VMs are isolated from host network
- Multiple VMs share the same network

**Advantages:**
- **VM-to-VM Communication:** Both systems can communicate directly
- **Internet Access:** Both VMs can download updates and packages
- **Network Isolation:** Separated from host network for security
- **No Host Configuration:** Works without modifying host network settings
- **Portable:** Configuration works on any host network

**Disadvantages:**
- **Port Forwarding Required:** Need to configure port forwarding for host access
- **IP Address Complexity:** DHCP addresses may change
- **Limited External Access:** Cannot be accessed directly from external networks

**Use Case:** Ideal for learning environments where VMs need to communicate but should be isolated from production networks.

#### Option 2: Bridged Adapter

**Characteristics:**
- VMs appear as physical devices on host network
- VMs get IP addresses from host DHCP server
- Direct communication with all network devices
- Accessible from any device on the network

**Advantages:**
- **Direct Access:** No port forwarding needed
- **Real Network Experience:** VMs behave like physical machines
- **External Accessibility:** Can be accessed from other network devices

**Disadvantages:**
- **Network Dependent:** Configuration tied to specific network
- **Security Concerns:** VMs exposed to network threats
- **IP Conflicts:** Potential conflicts with network DHCP
- **Not Portable:** Doesn't work on different networks without reconfiguration

#### Option 3: Host-Only Adapter

**Characteristics:**
- VMs can only communicate with host and each other
- No internet access unless manually configured
- Completely isolated private network

**Advantages:**
- **Complete Isolation:** Maximum security
- **Predictable IPs:** Static IP configuration
- **Host Control:** Full control over network

**Disadvantages:**
- **No Internet:** Requires additional adapter for internet access
- **Complex Setup:** More configuration required
- **Limited Utility:** Not suitable when internet access is needed

### IP Addressing Scheme

#### NAT Network Configuration

**Network Range:** 10.0.2.0/24
**Gateway:** 10.0.2.1
**DHCP Range:** 10.0.2.15 - 10.0.2.254
**DNS:** Provided by host

**IP Assignments:**
- **Server:** 10.0.2.15 (DHCP) or static configuration
- **Workstation:** 10.0.2.16 (DHCP) or static configuration

**Static IP Configuration (Optional):**

To configure static IPs, edit `/etc/netplan/00-installer-config.yaml` on Ubuntu:

```yaml
network:
  version: 2
  ethernets:
    enp0s3:
      addresses:
        - 10.0.2.15/24
      gateway4: 10.0.2.1
      nameservers:
        addresses:
          - 8.8.8.8
          - 8.8.4.4
```

Apply with: `sudo netplan apply`

### Port Forwarding Configuration

To enable SSH access from host to server:

**VirtualBox Port Forwarding Rule:**
- Name: SSH
- Protocol: TCP
- Host IP: 127.0.0.1
- Host Port: 2222
- Guest IP: 10.0.2.15
- Guest Port: 22

**Connection from Host:**
```bash
ssh -p 2222 username@localhost
```

### Firewall Configuration

**Ubuntu Server Firewall (ufw):**
```bash
sudo ufw enable
sudo ufw allow 22/tcp    # SSH
sudo ufw allow 80/tcp    # HTTP (if needed)
sudo ufw allow 443/tcp   # HTTPS (if needed)
sudo ufw status
```

**Ubuntu Desktop Firewall:**
```bash
sudo ufw enable
sudo ufw allow from 10.0.2.0/24  # Allow local network
sudo ufw status
```

### Network Testing

**Verify Network Connectivity:**

```bash
# Test internet connectivity
ping -c 4 8.8.8.8

# Test DNS resolution
ping -c 4 google.com

# Test VM-to-VM communication (from workstation)
ping -c 4 10.0.2.15

# Test SSH connectivity (from workstation to server)
ssh username@10.0.2.15
```

### Network Configuration Summary

| Aspect | Configuration |
|--------|---------------|
| Network Type | NAT Network |
| Network Range | 10.0.2.0/24 |
| Server IP | 10.0.2.15 |
| Workstation IP | 10.0.2.16 |
| Gateway | 10.0.2.1 |
| DNS | Host DNS (auto) |
| Internet Access | Yes (via NAT) |
| VM-to-VM | Yes |
| Host-to-VM | Via port forwarding |

---

## 5. System Specifications Documentation

### Purpose

This section documents the baseline system specifications using command-line tools. These commands provide essential information about system hardware, memory, storage, and network configuration.

### Server System Specifications

#### Command: `uname -a`

**Purpose:** Display system information including kernel version, hostname, and architecture.

**Expected Output:**
```
Linux ubuntu-server 5.15.0-58-generic #64-Ubuntu SMP Thu Jan 5 11:43:13 UTC 2023 x86_64 x86_64 x86_64 GNU/Linux
```

**Interpretation:**
- **Kernel:** Linux 5.15.0-58-generic
- **Operating System:** Ubuntu
- **Architecture:** x86_64 (64-bit)
- **Kernel Build Date:** January 5, 2023

**Breakdown:**
- `Linux`: Operating system kernel
- `ubuntu-server`: Hostname
- `5.15.0-58-generic`: Kernel version
- `#64-Ubuntu SMP`: Kernel build number and type (Symmetric Multi-Processing)
- `x86_64 x86_64 x86_64`: Processor architecture (64-bit)
- `GNU/Linux`: Operating system type

---

#### Command: `free -h`

**Purpose:** Display memory usage in human-readable format.

**Expected Output:**
```
              total        used        free      shared  buff/cache   available
Mem:           2.0Gi       450Mi       1.2Gi        12Mi       350Mi       1.4Gi
Swap:          2.0Gi          0B       2.0Gi
```

**Interpretation:**

**Physical Memory (RAM):**
- **Total:** 2.0 GB allocated to VM
- **Used:** 450 MB actively used by processes
- **Free:** 1.2 GB completely unused
- **Shared:** 12 MB shared between processes (tmpfs, IPC)
- **Buff/Cache:** 350 MB used for disk buffers and cache (reclaimable)
- **Available:** 1.4 GB available for new processes (free + reclaimable cache)

**Swap Space:**
- **Total:** 2.0 GB swap partition
- **Used:** 0 B (no swapping occurring - good sign)
- **Free:** 2.0 GB available swap

**Analysis:**
- System has adequate free memory
- No swapping indicates good performance
- Buffer/cache improving disk I/O performance
- Healthy memory utilization (~22% used)

---

#### Command: `df -h`

**Purpose:** Display disk space usage in human-readable format.

**Expected Output:**
```
Filesystem      Size  Used Avail Use% Mounted on
/dev/sda1        20G  4.5G   15G  24% /
tmpfs           1.0G     0  1.0G   0% /dev/shm
tmpfs           391M  1.2M  390M   1% /run
tmpfs           5.0M     0  5.0M   0% /run/lock
/dev/sda15      105M  5.3M  100M   5% /boot/efi
tmpfs           196M     0  196M   0% /run/user/1000
```

**Interpretation:**

**Primary Partition (/dev/sda1):**
- **Size:** 20 GB total capacity
- **Used:** 4.5 GB (operating system + installed packages)
- **Available:** 15 GB free space
- **Usage:** 24% (healthy utilization)
- **Mount Point:** / (root filesystem)

**Boot Partition (/dev/sda15):**
- **Size:** 105 MB
- **Used:** 5.3 MB (bootloader and kernel)
- **Available:** 100 MB
- **Usage:** 5%
- **Mount Point:** /boot/efi (EFI boot partition)

**Temporary Filesystems (tmpfs):**
- RAM-based filesystems for temporary data
- `/dev/shm`: Shared memory
- `/run`: Runtime data
- `/run/lock`: Lock files
- `/run/user/1000`: User-specific runtime data

**Analysis:**
- Adequate free disk space (15 GB available)
- Operating system using ~4.5 GB (typical for Ubuntu Server)
- No disk space concerns
- Healthy partition structure

---

#### Command: `ip addr`

**Purpose:** Display network interface configuration and IP addresses.

**Expected Output:**
```
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever

2: enp0s3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 08:00:27:3a:52:1c brd ff:ff:ff:ff:ff:ff
    inet 10.0.2.15/24 brd 10.0.2.255 scope global dynamic enp0s3
       valid_lft 86356sec preferred_lft 86356sec
    inet6 fe80::a00:27ff:fe3a:521c/64 scope link
       valid_lft forever preferred_lft forever
```

**Interpretation:**

**Interface 1: lo (Loopback)**
- **Purpose:** Local communication within the system
- **Status:** UP (active)
- **IPv4 Address:** 127.0.0.1/8
- **IPv6 Address:** ::1/128
- **Usage:** Internal processes communication

**Interface 2: enp0s3 (Primary Network Interface)**
- **Status:** UP, LOWER_UP (physically and logically connected)
- **MAC Address:** 08:00:27:3a:52:1c (VirtualBox prefix: 08:00:27)
- **IPv4 Address:** 10.0.2.15/24 (NAT network address)
- **Broadcast:** 10.0.2.255
- **Assignment:** Dynamic (DHCP)
- **MTU:** 1500 bytes (standard Ethernet)
- **IPv6 Link-Local:** fe80::a00:27ff:fe3a:521c/64

**Analysis:**
- Network interface properly configured
- Successfully obtained IP via DHCP
- Both IPv4 and IPv6 enabled
- Interface physically connected and operational

---

#### Command: `lsb_release -a`

**Purpose:** Display Linux Standard Base and distribution information.

**Expected Output:**
```
No LSB modules are available.
Distributor ID: Ubuntu
Description:    Ubuntu 22.04.1 LTS
Release:        22.04
Codename:       jammy
```

**Interpretation:**
- **Distribution:** Ubuntu
- **Version:** 22.04.1 LTS (Long-Term Support)
- **Release Number:** 22.04 (Released April 2022)
- **Codename:** Jammy Jellyfish
- **Support:** Until 2027 (5 years from release)

**Significance:**
- LTS version ensures stability and long-term support
- Jammy Jellyfish is the current stable LTS release
- Receives security updates and bug fixes
- Suitable for production and learning environments

---

### Workstation System Specifications

#### Command: `uname -a`

**Expected Output:**
```
Linux ubuntu-workstation 5.15.0-58-generic #64-Ubuntu SMP Thu Jan 5 11:43:13 UTC 2023 x86_64 x86_64 x86_64 GNU/Linux
```

**Analysis:** Same kernel version as server, ensuring compatibility and consistent behavior.

---

#### Command: `free -h`

**Expected Output:**
```
              total        used        free      shared  buff/cache   available
Mem:           4.0Gi       1.2Gi       1.8Gi        85Mi       1.0Gi       2.5Gi
Swap:          2.0Gi          0B       2.0Gi
```

**Analysis:**
- **Total RAM:** 4.0 GB (double the server allocation)
- **Used:** 1.2 GB (higher due to GUI desktop environment)
- **Available:** 2.5 GB (adequate for desktop applications)
- **Shared:** 85 MB (GUI applications sharing memory)
- **Desktop Overhead:** GUI consumes ~750 MB more than server

---

#### Command: `df -h`

**Expected Output:**
```
Filesystem      Size  Used Avail Use% Mounted on
/dev/sda1        25G  8.2G   16G  35% /
tmpfs           2.0G   48M  2.0G   3% /dev/shm
tmpfs           783M  2.1M  781M   1% /run
tmpfs           5.0M  4.0K  5.0M   1% /run/lock
/dev/sda15      105M  5.3M  100M   5% /boot/efi
tmpfs           392M   76K  392M   1% /run/user/1000
```

**Analysis:**
- **Total Storage:** 25 GB (5 GB more than server)
- **Used:** 8.2 GB (desktop environment + applications require more space)
- **Available:** 16 GB (adequate for development and coursework)
- **Desktop Overhead:** ~3.7 GB more than server

---

#### Command: `ip addr`

**Expected Output:**
```
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever

2: enp0s3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 08:00:27:7b:8f:2d brd ff:ff:ff:ff:ff:ff
    inet 10.0.2.16/24 brd 10.0.2.255 scope global dynamic enp0s3
       valid_lft 86295sec preferred_lft 86295sec
    inet6 fe80::a00:27ff:fe7b:8f2d/64 scope link
       valid_lft forever preferred_lft forever
```

**Analysis:**
- **IP Address:** 10.0.2.16 (different from server: 10.0.2.15)
- **Same Network:** Both on 10.0.2.0/24 subnet
- **MAC Address:** Different from server (08:00:27:7b:8f:2d)
- **Connectivity:** Can communicate with server at 10.0.2.15

---

#### Command: `lsb_release -a`

**Expected Output:**
```
No LSB modules are available.
Distributor ID: Ubuntu
Description:    Ubuntu 22.04.1 LTS
Release:        22.04
Codename:       jammy
```

**Analysis:** Identical distribution to server, ensuring compatibility and consistent package management.

---

### System Specifications Summary Table

| Component | Server | Workstation |
|-----------|--------|-------------|
| **Operating System** | Ubuntu Server 22.04 LTS | Ubuntu Desktop 22.04 LTS |
| **Kernel Version** | 5.15.0-58-generic | 5.15.0-58-generic |
| **Architecture** | x86_64 (64-bit) | x86_64 (64-bit) |
| **RAM Allocated** | 2.0 GB | 4.0 GB |
| **RAM Used** | ~450 MB | ~1.2 GB |
| **Swap Space** | 2.0 GB | 2.0 GB |
| **Disk Total** | 20 GB | 25 GB |
| **Disk Used** | 4.5 GB (24%) | 8.2 GB (35%) |
| **Disk Available** | 15 GB | 16 GB |
| **Network Interface** | enp0s3 | enp0s3 |
| **IP Address** | 10.0.2.15/24 | 10.0.2.16/24 |
| **Gateway** | 10.0.2.1 | 10.0.2.1 |
| **DNS** | Host DNS | Host DNS |
| **vCPUs** | 2 cores | 2 cores |

### Additional System Information Commands

#### CPU Information
```bash
lscpu
# Shows: Architecture, CPU cores, threads, vendor, model name, MHz
```

#### Detailed Hardware Info
```bash
sudo lshw -short
# Displays: All hardware components with brief descriptions
```

#### PCI Devices
```bash
lspci
# Lists: All PCI devices including network, storage, graphics
```

#### Block Devices
```bash
lsblk
# Shows: All block devices with mount points and sizes
```

#### Process List
```bash
ps aux
# Displays: All running processes with resource usage
```

#### System Uptime
```bash
uptime
# Shows: System uptime, user count, load averages
```

---

## Conclusion

This journal documents the comprehensive planning and configuration of a dual-system virtualized environment using VirtualBox. The key accomplishments include:

### Key Outcomes

1. **Architecture Design:** Created a clear system architecture with server and workstation VMs connected via NAT network

2. **Distribution Selection:** Justified the selection of Ubuntu Server and Desktop 22.04 LTS based on stability, support, learning resources, and industry relevance

3. **Workstation Configuration:** Selected full desktop environment to balance productivity, learning efficiency, and course requirements

4. **Network Configuration:** Implemented NAT network providing VM-to-VM communication, internet access, and security through isolation

5. **System Documentation:** Comprehensively documented system specifications using standard Linux commands (`uname`, `free`, `df`, `ip addr`, `lsb_release`)

### Technical Decisions Summary

| Decision Point | Choice | Rationale |
|----------------|--------|-----------|
| Server OS | Ubuntu Server 22.04 LTS | Stability, support, learning resources |
| Workstation OS | Ubuntu Desktop 22.04 LTS | Productivity, GUI tools, documentation needs |
| Network Type | NAT Network | VM communication + isolation |
| Server Resources | 2GB RAM, 20GB disk | Adequate for server services |
| Workstation Resources | 4GB RAM, 25GB disk | Sufficient for GUI + development |

### Learning Outcomes

Through this planning phase, I have:

1. **Understood System Architecture:** Learned how to design and document multi-system environments
2. **Evaluated Distributions:** Compared multiple Linux distributions and justified technical selections
3. **Configured Virtual Networks:** Understood VirtualBox networking options and their use cases
4. **Documented Systems:** Used CLI tools to gather and interpret system information
5. **Made Justified Decisions:** Provided technical rationale for each configuration choice

### Next Steps

With this foundation in place, subsequent phases will involve:

1. **Phase 2:** System installation and initial configuration
2. **Phase 3:** Service deployment and management
3. **Phase 4:** Security hardening and monitoring
4. **Phase 5:** Performance optimization and troubleshooting

The carefully planned architecture and well-justified technical decisions provide a solid foundation for practical operating system learning and administration throughout the course.

---

## References

### Official Documentation
1. Ubuntu Server Documentation: https://ubuntu.com/server/docs
2. Ubuntu Desktop Documentation: https://help.ubuntu.com/
3. VirtualBox User Manual: https://www.virtualbox.org/manual/
4. Linux man pages: `man` command for each tool documented

### Distribution Resources
5. Ubuntu Releases: https://wiki.ubuntu.com/Releases
6. Debian Documentation: https://www.debian.org/doc/
7. Rocky Linux Docs: https://docs.rockylinux.org/
8. Arch Wiki: https://wiki.archlinux.org/

### Networking Resources
9. VirtualBox Networking Modes: https://www.virtualbox.org/manual/ch06.html
10. Netplan Configuration: https://netplan.io/
11. Ubuntu Networking Guide: https://ubuntu.com/server/docs/network-introduction

### Command References
12. Linux Command Library: https://ss64.com/bash/
13. The Linux Documentation Project: https://tldp.org/
14. Ubuntu Community Wiki: https://help.ubuntu.com/community/

### Books
15. Evi Nemeth, et al. (2017). *UNIX and Linux System Administration Handbook* (5th ed.). Addison-Wesley.
16. Michael Jang (2020). *RHCSA/RHCE Red Hat Linux Certification Study Guide* (7th ed.). McGraw-Hill.

---

**End of Journal - Phase 1: System Planning and Distribution Selection**

*This journal provides comprehensive documentation of the planning phase, including architecture design, distribution selection justification, workstation configuration decisions, network configuration, and system specifications documentation. All deliverables for Assessment Week 1 have been addressed.*
