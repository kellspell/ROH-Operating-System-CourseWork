# Week 7 Journal: Process Management and Initial Security Configuration

**Course:** Operating Systems
**Instructors:** Tanaya Bowade & Dr Shabih Fatima
**Date:** Week 7
**Student:** [Your Name]

---

## Table of Contents
1. [Learning Objectives](#learning-objectives)
2. [Pre-Lab Preparation](#pre-lab-preparation)
3. [Part 1: Process Fundamentals and Management](#part-1-process-fundamentals-and-management)
4. [Part 2: SSH Key-Based Authentication Setup](#part-2-ssh-key-based-authentication-setup)
5. [Part 3: Firewall Configuration and User Management](#part-3-firewall-configuration-and-user-management)
6. [Reflection](#reflection)
7. [Conclusion](#conclusion)

---

## Learning Objectives

This week's lab session focused on:
- Understanding process lifecycle and states
- Using command-line tools for process monitoring
- Managing system processes effectively
- Implementing coursework security controls

---

## Pre-Lab Preparation

Before the lab session, I watched the following video lectures:
- ✅ Process Management Fundamentals
- ✅ Understanding System Monitoring Tools
- ✅ Process States and Lifecycle
- ✅ Operating System Structure

---

## Part 1: Process Fundamentals and Management

### Task 1.1: Exploring Process States

#### Objective
Learn to view and understand process information using various command-line tools.

#### Commands Executed

**1. Viewing all running processes:**
```bash
ps aux
```

**Screenshot:**
[Insert screenshot of ps aux output here]

**Key Columns Identified:**
- **USER**: The user who owns the process
- **PID**: Process identification number (unique identifier)
- **%CPU**: Percentage of CPU usage
- **%MEM**: Percentage of memory usage
- **STAT**: Current process state
- **COMMAND**: The command that started the process

**2. Comparing different process listing formats:**
```bash
ps -ef
```

**Screenshot:**
[Insert screenshot of ps -ef output here]

**Explanation:**
The `ps -ef` command shows processes in a different format, displaying:
- Full command paths
- Parent process IDs (PPID)
- Start times
- Different column arrangement compared to `ps aux`

**3. Real-time process monitoring:**
```bash
top
```

**Screenshot:**
[Insert screenshot of top command output here]

**Observations:**
- Real-time updates of CPU and memory usage
- Processes sorted by CPU usage by default
- Interactive interface (press 'q' to quit)
- Shows system summary at the top (uptime, load average, CPU states, memory usage)

**4. Enhanced monitoring with htop:**
```bash
sudo apt install htop
htop
```

**Screenshot:**
[Insert screenshot of htop output here]

**Advantages of htop over top:**
- Color-coded output for better readability
- Visual representation of CPU and memory usage with bars
- Mouse support for selecting processes
- Easier to navigate and more user-friendly
- Tree view of processes available

#### Process States Explained

| State | Symbol | Description |
|-------|--------|-------------|
| **Running** | R | Process is currently executing or ready to run |
| **Sleeping (Interruptible)** | S | Process is waiting for an event to complete (can be interrupted) |
| **Sleeping (Uninterruptible)** | D | Process is waiting for I/O operations (cannot be interrupted) |
| **Zombie** | Z | Process has completed but parent hasn't read its exit status |
| **Stopped** | T | Process has been stopped by job control signal or debugger |

**Examples from my system:**
[Document specific examples you observed]

---

### Task 1.2: Process Relationships and Control

#### 1. Viewing Process Hierarchy

**Commands:**
```bash
pstree
pstree -p
```

**Screenshot:**
[Insert screenshot of pstree output here]

**Explanation:**
- `pstree` displays processes in a tree structure showing parent-child relationships
- The `-p` flag shows Process IDs alongside process names
- Helps understand how processes spawn other processes
- Shows the init system (systemd) as the root of the process tree

---

#### 2. Background Process Management

**Starting a background process:**
```bash
sleep 300 &
jobs
```

**Screenshot:**
[Insert screenshot showing background process and jobs output here]

**Explanation:**
- The `&` symbol runs the process in the background
- `jobs` command lists all background jobs in the current shell
- Each job is assigned a job number (e.g., [1], [2])

---

#### 3. Process Control Practice

**Commands executed:**
```bash
sleep 500
# Pressed Ctrl+Z to suspend
jobs
bg
fg
```

**Screenshot:**
[Insert screenshot showing process control sequence here]

**Process Control Explained:**
- **Ctrl+Z**: Suspends (stops) the foreground process
- **jobs**: Lists all jobs with their status (running, stopped)
- **bg**: Resumes the suspended job in the background
- **fg**: Brings the background job to the foreground

**When to use foreground vs background:**
- **Foreground**: For interactive tasks requiring user input (e.g., text editors, interactive shells)
- **Background**: For long-running tasks that don't need interaction (e.g., file transfers, compilation, backups)

---

#### 4. Process Termination

**Commands executed:**
```bash
sleep 600 &
kill [PID]

sleep 600 &
sleep 600 &
killall sleep
```

**Screenshot:**
[Insert screenshot showing process termination here]

**Difference between kill and kill -9:**

| Command | Signal | Behavior | Use Case |
|---------|--------|----------|----------|
| `kill [PID]` | SIGTERM (15) | Graceful termination - allows process to clean up resources | Default, recommended method |
| `kill -9 [PID]` | SIGKILL (9) | Forceful termination - immediate kill without cleanup | Use only when process doesn't respond to SIGTERM |

**Why graceful termination is preferred:**
- Allows process to close files properly
- Saves state and data
- Releases resources cleanly
- Prevents data corruption

---

#### 5. Process Priority Experiment

**Commands executed:**
```bash
nice -n 10 sleep 400 &
top
```

**Screenshot:**
[Insert screenshot showing nice value in top here]

**Explanation:**
- The `nice` command sets the priority of a process
- Nice values range from -20 (highest priority) to 19 (lowest priority)
- Default nice value is 0
- In this example, `-n 10` gives the process lower priority
- Observed in the NI column in `top` output

---

#### Process Lifecycle Summary

**Process Lifecycle Stages:**

1. **New**: Process is being created
2. **Ready**: Process is ready to run and waiting for CPU time
3. **Running**: Process is currently executing on a CPU
4. **Waiting**: Process is waiting for I/O or an event to occur
5. **Terminated**: Process has finished execution

**Diagram:**
```
  New → Ready ⇄ Running → Terminated
           ↓      ↑
           Waiting
```

**My understanding:**
[Explain your understanding of how processes transition between states]

---

## Part 2: SSH Key-Based Authentication Setup

### Task 2.1: Generating SSH Keys

**Commands executed:**
```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

**Screenshot:**
[Insert screenshot showing SSH key generation process here]

**Steps followed:**
1. Accepted default location: `~/.ssh/id_ed25519`
2. Set a secure passphrase: [Used strong passphrase]
3. Keys generated:
   - Private key: `~/.ssh/id_ed25519` (keep secret!)
   - Public key: `~/.ssh/id_ed25519.pub` (can be shared)

**Viewing the public key:**
```bash
cat ~/.ssh/id_ed25519.pub
```

**Screenshot:**
[Insert screenshot of public key here]

#### Why ed25519 is Recommended Over RSA

| Feature | ed25519 | RSA |
|---------|---------|-----|
| **Key Size** | 256 bits | 2048-4096 bits (larger) |
| **Security Level** | Equivalent to 3072-bit RSA | Varies by key size |
| **Speed** | Faster key generation and verification | Slower |
| **Resistance to Attacks** | Better resistance to timing attacks | Vulnerable to certain attacks |
| **Modern Standard** | Modern elliptic curve cryptography | Older algorithm |

**My explanation:**
[Provide your understanding of why ed25519 is better]

---

### Task 2.2: Copying Key to Server

**Commands executed:**
```bash
ssh-copy-id username@server_ip
# Entered password when prompted
```

**Screenshot:**
[Insert screenshot showing ssh-copy-id process here]

**Testing passwordless login:**
```bash
ssh username@server_ip
```

**Screenshot:**
[Insert screenshot showing successful passwordless SSH connection with visible command prompts showing username@hostname on both systems]

**How SSH key authentication works:**
1. Public key is copied to `~/.ssh/authorized_keys` on the server
2. When connecting, the server challenges the client with the public key
3. Client proves identity using the private key (without sending it)
4. No password is needed if keys match
5. Passphrase (if set) protects the private key locally

---

### Task 2.3: Hardening SSH Configuration

#### 1. Backup Original Configuration

**Commands executed:**
```bash
sudo cp /etc/ssh/sshd_config /etc/ssh/sshd_config.backup
```

**Screenshot:**
[Insert screenshot here]

**Why backup is important:**
- Allows reverting changes if something goes wrong
- Provides reference to original settings
- Standard security practice before modifying system files

---

#### 2. Editing SSH Configuration

**Commands executed:**
```bash
sudo nano /etc/ssh/sshd_config
```

**Before Configuration:**
[Insert screenshot of BEFORE sshd_config file showing relevant lines]

**Changes Made:**
```
PasswordAuthentication no
PubkeyAuthentication yes
PermitRootLogin no
```

**After Configuration:**
[Insert screenshot of AFTER sshd_config file showing the changes]

---

#### 3. Security Improvements Explained

| Setting | Value | Security Benefit |
|---------|-------|------------------|
| `PasswordAuthentication` | no | Prevents brute-force password attacks; forces key-based authentication |
| `PubkeyAuthentication` | yes | Enables SSH key authentication (more secure than passwords) |
| `PermitRootLogin` | no | Prevents direct root login; requires users to login with regular account and escalate privileges |

**Defense-in-Depth Strategy:**
By disabling root login, even if an attacker obtains valid credentials, they cannot directly access the root account. They must:
1. First authenticate as a regular user
2. Then escalate privileges (which creates an audit trail)

---

#### 4. Restarting SSH Service

**Commands executed:**
```bash
sudo systemctl restart sshd
```

**Screenshot:**
[Insert screenshot here]

**Verification from different terminal:**
[Insert screenshot showing that password authentication is now disabled]

**Important Note:**
Before logging out, I tested SSH access from another terminal to ensure key-based authentication works properly. This prevents being locked out of the server.

---

## Part 3: Firewall Configuration and User Management

### Task 3.1: Implementing Firewall Rules

#### 1. Checking UFW Status

**Commands executed:**
```bash
sudo ufw status
```

**Screenshot:**
[Insert screenshot of initial UFW status here]

#### 2. Installing UFW (if needed)

**Commands executed:**
```bash
sudo apt update
sudo apt install ufw
```

**Screenshot:**
[Insert screenshot if installation was needed]

---

#### 3. Setting Default Policies

**Commands executed:**
```bash
sudo ufw default deny incoming
sudo ufw default allow outgoing
```

**Screenshot:**
[Insert screenshot here]

**Why these defaults?**

| Policy | Direction | Justification |
|--------|-----------|---------------|
| Deny | Incoming | Blocks all unsolicited incoming connections (whitelist approach) - only explicitly allowed services can receive connections |
| Allow | Outgoing | Permits internal services to communicate externally - allows software updates, web browsing, etc. |

**Security Principle:**
This implements a "default deny" security posture - everything is blocked unless explicitly allowed.

---

#### 4. Allowing SSH from Workstation

**Commands executed:**
```bash
sudo ufw allow from [workstation_ip] to any port 22
```

**Screenshot:**
[Insert screenshot here]

**Security benefit:**
- SSH access is restricted to my known workstation IP only
- Blocks SSH attempts from all other IP addresses
- Significantly reduces attack surface for SSH brute-force attacks

**My workstation IP:** [Document your actual workstation IP]

---

#### 5. Enabling the Firewall

**Commands executed:**
```bash
sudo ufw enable
```

**Screenshot:**
[Insert screenshot here]

---

#### 6. Verifying Rules

**Commands executed:**
```bash
sudo ufw status numbered
sudo ufw status verbose
```

**Screenshot:**
[Insert screenshot showing complete firewall ruleset here]

#### Complete Firewall Ruleset Table

| Rule # | Action | From | To | Port | Protocol | Justification |
|--------|--------|------|-----|------|----------|---------------|
| 1 | ALLOW | [workstation_ip] | Any | 22 | TCP | Allow SSH access from my workstation only |
| [Add more rules if configured] | | | | | | |

**Defense-in-Depth Strategy Implementation:**

Multiple layers of security are now in place:

1. **Network Level (Firewall):**
   - UFW blocks unauthorized network connections
   - Only specific IPs can access SSH port

2. **Access Level (SSH Configuration):**
   - Key-based authentication required
   - Password authentication disabled
   - Root login disabled

3. **Authorization Level (User Privileges):**
   - Non-root administrative users
   - Sudo for privilege escalation
   - Audit trail of privileged actions

4. **Data Level:**
   - Encrypted SSH communications
   - Protected private keys with passphrases

**My understanding:**
[Explain how these layers work together to provide comprehensive security]

---

### Task 3.2: User and Privilege Management

#### 1. Creating Non-Root Administrative User

**Commands executed:**
```bash
sudo adduser adminuser
```

**Screenshot:**
[Insert screenshot showing user creation process with password prompt]

**Password Policy:**
I set a strong password following these criteria:
- Minimum 12 characters
- Mix of uppercase, lowercase, numbers, and symbols
- Not based on dictionary words

---

#### 2. Adding User to Sudo Group

**Commands executed:**
```bash
sudo usermod -aG sudo adminuser
```

**Screenshot:**
[Insert screenshot here]

**Explanation of the command:**
- `usermod`: Modifies a user account
- `-aG`: Appends (-a) to group (-G) without removing from other groups
- `sudo`: The group name
- `adminuser`: The username

---

#### 3. Verifying Group Membership

**Commands executed:**
```bash
groups adminuser
id adminuser
```

**Screenshot:**
[Insert screenshot showing group membership here]

**Output explanation:**
- `groups` command shows all groups the user belongs to
- `id` command shows user ID (UID), group ID (GID), and all groups
- Should see "sudo" in the list of groups

---

#### 4. Testing Sudo Access

**Commands executed:**
```bash
su - adminuser
sudo apt update
whoami
```

**Screenshot:**
[Insert screenshot showing sudo access test here]

**Verification:**
- Able to run `sudo apt update` successfully
- System prompted for adminuser's password
- Command executed with root privileges
- `whoami` shows I'm still logged in as adminuser (not root)

---

#### 5. Listing Users with Sudo Privileges

**Commands executed:**
```bash
getent group sudo
```

**Screenshot:**
[Insert screenshot here]

**Current users with sudo privileges:**
[List the users shown in the output]

---

#### Principle of Least Privilege

**Definition:**
Users and processes should have only the minimum permissions necessary to perform their tasks.

**How this applies to our configuration:**

1. **Regular Users:**
   - No administrative privileges by default
   - Cannot install software or modify system files
   - Limited to their own files and directories

2. **Administrative Users (with sudo):**
   - Normal user privileges by default
   - Can temporarily elevate to root privileges when needed
   - Must explicitly use `sudo` command
   - Each sudo command is logged

3. **Root Account:**
   - Direct login disabled (PermitRootLogin no)
   - Only accessible via `sudo` from authorized users
   - Creates accountability trail

**Benefits:**
- Reduces risk of accidental system damage
- Provides audit trail of privileged actions
- Limits damage from compromised accounts
- Follows security best practices

**Why non-root administrative users are important:**
[Provide your explanation]

---

### Task 3.3: Remote Administration Evidence

#### Remote Command Execution

**Commands executed from workstation:**

**1. System information:**
```bash
ssh username@server_ip 'uname -a'
```
[Insert screenshot]

**2. Memory information:**
```bash
ssh username@server_ip 'free -h'
```
[Insert screenshot]

**3. Disk space:**
```bash
ssh username@server_ip 'df -h'
```
[Insert screenshot]

**4. Firewall status:**
```bash
ssh username@server_ip 'sudo ufw status'
```
[Insert screenshot]

**5. SSH service status:**
```bash
ssh username@server_ip 'systemctl status sshd'
```
[Insert screenshot]

---

#### Interactive SSH Session

**Session transcript:**
```bash
ssh username@server_ip
pwd
hostname
ip addr show
exit
```

**Screenshot:**
[Insert screenshot showing interactive session with visible command prompts displaying username@hostname for both workstation and server]

**Workstation-to-Server Architecture:**

- **Workstation:** [Your workstation hostname/IP]
- **Server:** [Your server hostname/IP]
- **Connection Method:** SSH with key-based authentication
- **Administration Model:** All server administration performed remotely via SSH

**Evidence Requirements Met:**
- ✅ Multiple screenshots showing commands executed via SSH
- ✅ Evidence of workstation-to-server architecture
- ✅ Command prompts show username@hostname for both systems
- ✅ Demonstrates that server console is not used directly

---

## Reflection

### Challenges Encountered and Resolutions

**Challenge 1: [Describe a challenge]**
- **Problem:** [What went wrong]
- **Solution:** [How you fixed it]
- **Learning:** [What you learned]

**Challenge 2: [Describe another challenge]**
- **Problem:**
- **Solution:**
- **Learning:**

---

### Security Trade-offs Considered

**1. Convenience vs. Security:**
- Disabling password authentication improves security but requires careful key management
- If private key is lost and no backup exists, access to server is lost
- Solution: Keep secure backups of private keys

**2. Access Control vs. Usability:**
- Restricting SSH to specific IP addresses is very secure
- However, limits access if I need to connect from a different location
- Possible solution: VPN access or carefully managed IP whitelist

**3. Root Access Restrictions:**
- Disabling direct root login adds security layer
- Adds extra step (sudo) for administrative tasks
- Benefit outweighs inconvenience due to audit trail and reduced attack surface

---

### Connection Between Theory and Practice

**From Lectures to Implementation:**

1. **Process Management Theory:**
   - Lectures covered process states and lifecycle
   - Lab gave hands-on experience with `ps`, `top`, `kill` commands
   - Now understand how processes actually transition between states

2. **Authentication vs. Authorization:**
   - Theory explained the difference between these concepts
   - Practice: SSH keys implement authentication, file permissions implement authorization
   - Saw how both work together in a real system

3. **Defense-in-Depth:**
   - Lecture introduced the concept of layered security
   - Lab implemented multiple layers: firewall, SSH hardening, user privileges
   - Understand how each layer compensates for potential weaknesses in others

4. **Principle of Least Privilege:**
   - Covered in lecture as theoretical security principle
   - Implemented through non-root users, sudo configuration, file permissions
   - Appreciate the practical importance of this principle

---

### Key Learnings

**Technical Skills Gained:**
- Process monitoring and management using command-line tools
- SSH key generation and configuration
- Firewall configuration with UFW
- User and privilege management in Linux
- Remote system administration

**Security Concepts Reinforced:**
- Importance of initial security configuration
- How multiple security layers provide defense-in-depth
- Practical application of authentication mechanisms
- Audit trails and accountability

**Best Practices Learned:**
- Always backup configuration files before modification
- Test changes in a separate session before closing current session
- Document all changes for future reference
- Use strong passphrases for SSH keys
- Apply principle of least privilege consistently

---

### Areas for Improvement

**What I could do better:**
1. [Identify areas where you struggled or could improve]
2. [Additional security measures you could implement]
3. [Documentation practices you want to enhance]

**Next Steps:**
- [What you plan to learn or practice next]
- [Additional security hardening you want to explore]

---

## Conclusion

This week's lab provided hands-on experience with essential system administration and security tasks. The key achievements were:

1. ✅ Successfully configured SSH key-based authentication
2. ✅ Hardened SSH configuration by disabling password authentication and root login
3. ✅ Implemented firewall rules to restrict access
4. ✅ Created and managed users with appropriate privileges
5. ✅ Demonstrated remote administration capabilities
6. ✅ Gained practical understanding of process management

The combination of process management and security configuration skills forms a foundation for secure system administration. The defense-in-depth approach implemented through multiple security layers (firewall, SSH hardening, user privileges) demonstrates real-world security best practices.

---

## Technical Requirements Checklist

- [ ] All screenshots show visible command prompts with username@hostname
- [ ] Each command includes output and explanation
- [ ] System architecture diagram updated to show security controls
- [ ] Work committed and pushed to GitHub

**Git commands to run:**
```bash
cd /home/kellspell/Desktop/Operating-System/Week-7
git add Week-7-Journal.md
git commit -m "Week 7: Initial Security Configuration - Process Management and Security Implementation"
git push
```

---

**End of Week 7 Journal**
