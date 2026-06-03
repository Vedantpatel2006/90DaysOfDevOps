# Day 07 – Linux File System Hierarchy & Scenario-Based Practice

## Part 1: Linux File System Hierarchy

### `/` (Root Directory)

* The starting point of the Linux file system.
* All files and directories originate from here.

**Command:**

```bash
ls -l /
```

**Observed:**

* home
* etc
* var

**I would use this when:**
Navigating the overall Linux file system structure.

---

### `/home`

* Contains user home directories.
* Stores personal files and user-specific configurations.

**Command:**

```bash
ls -la /home
```

**Observed:**

* ubuntu
* user directories

**I would use this when:**
Managing user files and directories.

---

### `/root`

* Home directory for the root user.
* Accessible only with elevated privileges.

**Command:**

```bash
ls -la /root
```

**Observed:**

* .bashrc
* .profile

**I would use this when:**
Performing administrative tasks as root.

---

### `/etc`

* Stores system configuration files.
* Contains service and application configurations.

**Command:**

```bash
ls -l /etc | head
```

**Observed:**

* hostname
* hosts

**I would use this when:**
Troubleshooting or modifying system configurations.

---

### `/var/log`

* Stores system and application logs.
* Very important for troubleshooting.

**Command:**

```bash
ls -l /var/log | head
```

**Observed:**

* syslog
* auth.log

**I would use this when:**
Investigating service failures and system issues.

---

### `/tmp`

* Stores temporary files.
* Files may be removed after reboot.

**Command:**

```bash
ls -la /tmp
```

**Observed:**

* temporary folders
* temporary files

**I would use this when:**
Creating temporary test files.

---

### `/bin`

* Contains essential Linux command binaries.

**Command:**

```bash
ls -l /bin | head
```

**Observed:**

* common Linux utilities

**I would use this when:**
Understanding where system commands are stored.

---

### `/usr/bin`

* Contains user command binaries and applications.

**Command:**

```bash
ls -l /usr/bin | head
```

**Observed:**

* git
* ssh

**I would use this when:**
Finding installed commands and applications.

---

### `/opt`

* Used for optional or third-party software.

**Command:**

```bash
ls -l /opt
```

**Observed:**

* application folders

**I would use this when:**
Managing manually installed applications.

---

## Hands-On Tasks

### Largest Log Files

```bash
du -sh /var/log/* 2>/dev/null | sort -h | tail -5
```

**Observation:**
Identified the largest log files consuming disk space.

---

### Hostname Configuration

```bash
cat /etc/hostname
```

**Observation:**
Displayed the system hostname.

---

### Home Directory Check

```bash
ls -la ~
```

**Observation:**
Displayed user files and hidden configuration files.

---

# Part 2: Scenario-Based Practice

## Scenario 1: Service Not Starting

### Step 1

```bash
systemctl status myapp
```

Why: Check whether the service is active, failed, or stopped.

### Step 2

```bash
journalctl -u myapp -n 50
```

Why: Review recent service logs.

### Step 3

```bash
systemctl is-enabled myapp
```

Why: Verify if the service starts automatically after reboot.

### Step 4

```bash
systemctl list-units --type=service
```

Why: Check available services.

---

## Scenario 2: High CPU Usage

### Step 1

```bash
top
```

Why: Monitor CPU usage in real time.

### Step 2

```bash
ps aux --sort=-%cpu | head -10
```

Why: Identify processes consuming the most CPU.

### Step 3

Record the PID of the process using excessive CPU.

---

## Scenario 3: Finding Service Logs

### Step 1

```bash
systemctl status docker
```

Why: Verify service status.

### Step 2

```bash
journalctl -u docker -n 50
```

Why: View recent logs.

### Step 3

```bash
journalctl -u docker -f
```

Why: Follow logs in real time.

---

## Scenario 4: File Permission Issue

### Step 1

```bash
ls -l backup.sh
```

Why: Check current permissions.

### Step 2

```bash
chmod +x backup.sh
```

Why: Add execute permission.

### Step 3

```bash
ls -l backup.sh
```

Why: Verify permission change.

### Step 4

```bash
./backup.sh
```

Why: Execute the script.

---

## What I Learned

* Linux follows a structured file system hierarchy.
* `/etc` and `/var/log` are critical during troubleshooting.
* Logs should be checked before restarting services.
* CPU issues can be investigated using `top` and `ps`.
* File permissions directly affect script execution.

