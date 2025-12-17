# Operating Systems Journal - Week 3
## Lab Activity: Linux Distribution Comparison and Performance Monitoring

---

## Learning Objectives
- Explore and compare multiple Linux distributions for performance and usability
- Use performance monitoring tools to evaluate key system metrics
- Document and reflect on system performance data effectively

---

## Table of Contents
1. [Task 1: Setup and Exploration of Linux Distributions](#task-1-setup-and-exploration-of-linux-distributions)
2. [Task 2: Performance Monitoring Tools](#task-2-performance-monitoring-tools)
3. [Task 3: Documentation and Reflection](#task-3-documentation-and-reflection)
4. [Reflection & Discussion](#reflection--discussion)

---

## Task 1: Setup and Exploration of Linux Distributions

### Objective
Familiarize with at least two Linux distributions.

### Steps Completed

#### 1. Launch Two Virtual Machines

**Distribution 1:**
- **Name**: [Distribution name, e.g., Ubuntu 22.04 LTS]
- **Type**: [Desktop/Server]
- **VM Configuration**:
  - CPU: [Number of cores]
  - RAM: [Amount of RAM]
  - Disk: [Storage size]
  - Hypervisor: [VirtualBox/VMware/KVM]

**Distribution 2:**
- **Name**: [Distribution name, e.g., Fedora 38]
- **Type**: [Desktop/Server]
- **VM Configuration**:
  - CPU: [Number of cores]
  - RAM: [Amount of RAM]
  - Disk: [Storage size]
  - Hypervisor: [VirtualBox/VMware/KVM]

#### 2. Exploration of Key Components

##### Package Managers

**Distribution 1:**
- **Package Manager**: [e.g., APT (Advanced Package Tool)]
- **Commands**:
  - Update: `[command]`
  - Install: `[command]`
  - Remove: `[command]`
  - Search: `[command]`

**Distribution 2:**
- **Package Manager**: [e.g., DNF (Dandified YUM)]
- **Commands**:
  - Update: `[command]`
  - Install: `[command]`
  - Remove: `[command]`
  - Search: `[command]`

##### Default Services

**Distribution 1:**
- **Init System**: [e.g., systemd]
- **Key Services Running**:
  - [List of services]
  - [e.g., NetworkManager, firewalld, sshd]

**Distribution 2:**
- **Init System**: [e.g., systemd]
- **Key Services Running**:
  - [List of services]
  - [e.g., NetworkManager, firewalld, sshd]

##### Directory Structures

**Distribution 1:**
- **Unique Directories/Characteristics**:
  - [Notable directory structures]
  - [Configuration file locations]
  - [Package installation paths]

**Distribution 2:**
- **Unique Directories/Characteristics**:
  - [Notable directory structures]
  - [Configuration file locations]
  - [Package installation paths]

#### 3. Comparison Table

| Feature | Distribution 1 ([Name]) | Distribution 2 ([Name]) |
|---------|------------------------|------------------------|
| **Package Manager** | [e.g., APT] | [e.g., DNF] |
| **Update Command** | [e.g., sudo apt update] | [e.g., sudo dnf check-update] |
| **Install Command** | [e.g., sudo apt install] | [e.g., sudo dnf install] |
| **Init System** | [e.g., systemd] | [e.g., systemd] |
| **Default Shell** | [e.g., bash] | [e.g., bash] |
| **Firewall** | [e.g., ufw] | [e.g., firewalld] |
| **Config Directory** | [e.g., /etc] | [e.g., /etc] |
| **Package Cache** | [e.g., /var/cache/apt] | [e.g., /var/cache/dnf] |
| **Log Location** | [e.g., /var/log] | [e.g., /var/log] |
| **Default Services Count** | [Number] | [Number] |
| **Boot Time** | [Time in seconds] | [Time in seconds] |
| **Base Install Size** | [Size in GB] | [Size in GB] |

### Observations
[Document key differences observed between the two distributions in terms of usability, structure, and initial setup]

---

## Task 2: Performance Monitoring Tools

### Objective
Use monitoring tools to observe system performance.

### Steps Completed

#### 4. Install and Run Monitoring Tools

##### Installation on Distribution 1 ([Name])

**htop Installation:**
```bash
[Installation command and output]
```

**iotop Installation:**
```bash
[Installation command and output]
```

**nmon Installation:**
```bash
[Installation command and output]
```

##### Installation on Distribution 2 ([Name])

**htop Installation:**
```bash
[Installation command and output]
```

**iotop Installation:**
```bash
[Installation command and output]
```

**nmon Installation:**
```bash
[Installation command and output]
```

#### 5. Observe CPU, Memory, and I/O Usage

##### Scenario 1: Idle System

**Distribution 1 - Idle State:**
- **CPU Usage**: [Percentage and observations]
  - User: [%]
  - System: [%]
  - Idle: [%]
- **Memory Usage**: [Amount used/total]
  - Used: [Amount]
  - Free: [Amount]
  - Cached: [Amount]
- **I/O Usage**: [Disk read/write rates]
  - Read: [MB/s]
  - Write: [MB/s]

**Distribution 2 - Idle State:**
- **CPU Usage**: [Percentage and observations]
  - User: [%]
  - System: [%]
  - Idle: [%]
- **Memory Usage**: [Amount used/total]
  - Used: [Amount]
  - Free: [Amount]
  - Cached: [Amount]
- **I/O Usage**: [Disk read/write rates]
  - Read: [MB/s]
  - Write: [MB/s]

##### Scenario 2: During System Updates

**Distribution 1 - During Updates:**
- **Command Used**: [e.g., sudo apt update && sudo apt upgrade]
- **CPU Usage**: [Percentage and observations]
  - Peak: [%]
  - Average: [%]
- **Memory Usage**: [Amount used]
  - Peak: [Amount]
  - Average: [Amount]
- **I/O Usage**: [Disk activity]
  - Peak Read: [MB/s]
  - Peak Write: [MB/s]
  - Processes involved: [List from iotop]

**Distribution 2 - During Updates:**
- **Command Used**: [e.g., sudo dnf update]
- **CPU Usage**: [Percentage and observations]
  - Peak: [%]
  - Average: [%]
- **Memory Usage**: [Amount used]
  - Peak: [Amount]
  - Average: [Amount]
- **I/O Usage**: [Disk activity]
  - Peak Read: [MB/s]
  - Peak Write: [MB/s]
  - Processes involved: [List from iotop]

##### Scenario 3: File Copy Operations

**Test Setup:**
- **File Size**: [e.g., 1GB test file]
- **Copy Command**: [e.g., cp large_file.iso /tmp/]

**Distribution 1 - File Copy:**
- **CPU Usage**: [Percentage and observations]
- **Memory Usage**: [Amount used]
- **I/O Usage**: [Detailed disk activity]
  - Read Speed: [MB/s]
  - Write Speed: [MB/s]
  - I/O Wait: [%]
- **Time Taken**: [Seconds]

**Distribution 2 - File Copy:**
- **CPU Usage**: [Percentage and observations]
- **Memory Usage**: [Amount used]
- **I/O Usage**: [Detailed disk activity]
  - Read Speed: [MB/s]
  - Write Speed: [MB/s]
  - I/O Wait: [%]
- **Time Taken**: [Seconds]

#### 6. Screenshots and Observations

##### htop Screenshots
**Distribution 1:**
- [Screenshot location or description]
- **Key Observations**:
  - [Notable process behavior]
  - [Resource usage patterns]

**Distribution 2:**
- [Screenshot location or description]
- **Key Observations**:
  - [Notable process behavior]
  - [Resource usage patterns]

##### iotop Screenshots
**Distribution 1:**
- [Screenshot location or description]
- **Key Observations**:
  - [I/O intensive processes]
  - [Disk throughput]

**Distribution 2:**
- [Screenshot location or description]
- **Key Observations**:
  - [I/O intensive processes]
  - [Disk throughput]

##### nmon Screenshots
**Distribution 1:**
- [Screenshot location or description]
- **Key Observations**:
  - [Overall system performance]
  - [Resource utilization patterns]

**Distribution 2:**
- [Screenshot location or description]
- **Key Observations**:
  - [Overall system performance]
  - [Resource utilization patterns]

---

## Task 3: Documentation and Reflection

### Objective
Summarize findings and reflect on performance differences.

#### 7. Summary of Setup, Tests, and Key Results

##### Setup Summary
[Provide a concise summary of the VM setup process, including any challenges encountered and how they were resolved]

##### Test Summary
[Summarize the three testing scenarios: idle state, system updates, and file copy operations]

##### Key Results
- **Performance Winner**: [Which distribution performed better overall]
- **CPU Efficiency**: [Comparison of CPU usage between distributions]
- **Memory Efficiency**: [Comparison of memory usage between distributions]
- **I/O Performance**: [Comparison of disk I/O performance between distributions]
- **Boot Time**: [Comparison of boot times]
- **Update Process**: [Comparison of update efficiency]

#### 8. Screenshots and Explanations

##### Screenshot 1: [Description]
- **Location**: [Path or reference]
- **Explanation**: [What the screenshot shows and why it's significant]

##### Screenshot 2: [Description]
- **Location**: [Path or reference]
- **Explanation**: [What the screenshot shows and why it's significant]

##### Screenshot 3: [Description]
- **Location**: [Path or reference]
- **Explanation**: [What the screenshot shows and why it's significant]

[Continue for all relevant screenshots]

#### 9. Reflection on Distribution Efficiency

##### Overall Performance Assessment
[Detailed reflection on which distribution was more efficient and why, considering all test scenarios]

##### Specific Strengths and Weaknesses

**Distribution 1 ([Name]):**
- **Strengths**:
  - [List strengths based on observations]
  - [e.g., Lower idle resource usage]
  - [e.g., Faster package management]

- **Weaknesses**:
  - [List weaknesses based on observations]
  - [e.g., Higher CPU usage during updates]

**Distribution 2 ([Name]):**
- **Strengths**:
  - [List strengths based on observations]
  - [e.g., Better I/O performance]
  - [e.g., More efficient memory management]

- **Weaknesses**:
  - [List weaknesses based on observations]
  - [e.g., Longer boot time]

---

## Reflection & Discussion

### Which distribution performed better and why?

[Provide a detailed answer discussing:
- Overall performance metrics
- Specific use cases where one distribution excelled
- Quantitative data supporting the conclusion
- Qualitative observations about usability and efficiency]

### What factors affected CPU and I/O usage?

#### CPU Usage Factors
[Analyze factors that influenced CPU usage:
- Background services and daemons
- Default system configuration
- Package manager efficiency
- Process scheduling
- Number of default running processes]

#### I/O Usage Factors
[Analyze factors that influenced I/O usage:
- Filesystem type and configuration
- Disk cache settings
- Package manager caching strategies
- Update mechanisms
- Default system logging]

### How might these findings inform system selection for specific workloads?

#### Workload-Based Recommendations

##### Lightweight/Resource-Constrained Environments
[Based on the findings, which distribution would be better for systems with limited resources and why]

##### Server/Enterprise Workloads
[Based on the findings, which distribution would be better for server environments and why]

##### Development Workstations
[Based on the findings, which distribution would be better for development work and why]

##### High-I/O Applications
[Based on the findings, which distribution would be better for I/O intensive applications and why]

#### General Recommendations
[Provide general guidance on selecting distributions based on specific requirements, drawing from the lab observations]

---

## Conclusion

### Key Learnings
[Summarize the most important insights gained from this lab activity]

### Practical Applications
[Describe how these learnings can be applied in real-world scenarios]

### Areas for Further Investigation
[Identify topics or tests that could be explored further to deepen understanding]

---

**Lab Activity Completed:** Week 3
**Date:** [Date]
**Distributions Compared:** [Distribution 1] vs [Distribution 2]
**Tools Used:** htop, iotop, nmon
