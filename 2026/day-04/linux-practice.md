# Day 04 – Linux Practice: Processes and Services

## Process Checks

### Command 1

```bash
ps aux | head
```

### Observation

Displayed the first few running processes on the system, including the init process and kernel threads.

### What I Learned

This command helps inspect currently running processes and their resource usage.

---

### Command 2

```bash
top
```

### Observation

Displayed real-time CPU usage, memory usage, load average, and active processes.

### What I Learned

The `top` command is useful for monitoring system performance and identifying resource-intensive processes.

---

## Service Checks

### Command 3

```bash
systemctl status ssh
```

### Observation

The SSH service was active and running.

```text
ssh.service - OpenBSD Secure Shell server
Active: active (running)
```

### What I Learned

This command helps verify the status of a service and shows recent service activity.

---

### Command 4

```bash
systemctl list-units --type=service
```

### Observation

Listed all active services currently running on the system.

### What I Learned

This command provides a quick overview of system services managed by systemd.

---

## Log Checks

### Command 5

```bash
tail -n 50 app.log
```

### Observation

Displayed the latest 50 log entries from the application log file.

### What I Learned

The `tail` command is useful for viewing recent log activity during troubleshooting.

---

### Command 6

```bash
journalctl -u ssh -n 20
```

### Observation

Displayed the most recent SSH service log entries.

### What I Learned

`journalctl` helps analyze service logs and diagnose issues related to system services.

---

## Mini Troubleshooting

### Service Inspected

SSH Service

### Steps Performed

1. Checked running processes using `ps aux | head`.
2. Monitored system activity using `top`.
3. Verified SSH service status using `systemctl status ssh`.
4. Listed active services using `systemctl list-units --type=service`.
5. Reviewed recent logs using `tail -n 50 app.log`.
6. Inspected SSH logs using `journalctl -u ssh -n 20`.

### Conclusion

Today I practiced Linux process monitoring, service management, and log inspection. These commands are essential for troubleshooting and maintaining Linux servers in real-world DevOps environments.

