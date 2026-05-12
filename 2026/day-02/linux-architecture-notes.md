# Linux Architecture, Processes, and systemd

## 1. Core Components of Linux

### Kernel
- Core part of Linux OS
- Manages:
  - CPU
  - Memory
  - Devices
  - Filesystem
  - Processes
- Acts as bridge between hardware and software

### User Space
- Area where user applications run
- Examples:
  - Bash
  - Chrome
  - VS Code
  - Nginx
- Users interact with Linux through user space programs

### Init / systemd
- First process started by kernel (PID 1)
- Responsible for:
  - Starting services
  - Managing background processes
  - Boot process
  - Logging and restarting failed services

## 2. Process Management

### What is a Process?
- A running instance of a program
- Every process has:
  - PID (Process ID)
  - Parent Process
  - Memory allocation
  - State

### Process Creation
- New processes are created using:
  - fork() → creates copy of process
  - exec() → loads new program into memory

### Process States
| State | Meaning |
|------|---------|
| Running | Currently executing |
| Sleeping | Waiting for event/input |
| Stopped | Paused process |
| Zombie | Finished but entry still exists |
| Orphan | Parent process terminated |

## 3. What systemd Does

### systemd
- Modern Linux init system
- Handles:
  - Service management
  - Boot sequence
  - Logging
  - Scheduling

### Why systemd Matters
- Auto restarts failed services
- Faster boot process
- Centralized service management
- Used in most modern Linux distributions

### Useful systemd Commands
```bash
systemctl status nginx
systemctl start nginx
systemctl stop nginx
systemctl restart nginx
journalctl -u nginx
