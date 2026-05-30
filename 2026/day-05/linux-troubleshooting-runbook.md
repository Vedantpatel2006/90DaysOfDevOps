# Day 05 – Linux Troubleshooting Runbook

## Target Service

SSH Service (`ssh.service`)

---

## Environment Basics

### Command

```bash
uname -a
```

### Observation

Displayed Ubuntu Linux kernel version and system architecture.

---

### Command

```bash
cat /etc/os-release
```

### Observation

Confirmed Ubuntu operating system details.

---

## Filesystem Sanity Check

### Command

```bash
mkdir /tmp/runbook-demo
cp /etc/hosts /tmp/runbook-demo/hosts-copy
ls -l /tmp/runbook-demo
```

### Observation

Successfully created a test directory and copied a file.

---

## CPU & Memory Snapshot

### Command

```bash
top -b -n 1 | head -15
```

### Observation

CPU utilization was low and no abnormal resource consumption was detected.

---

### Command

```bash
free -h
```

### Observation

Memory usage was within normal limits with available free memory.

---

## Disk & IO Snapshot

### Command

```bash
df -h
```

### Observation

Disk usage was healthy and no filesystem was close to full capacity.

---

### Command

```bash
du -sh /var/log
```

### Observation

Checked total log directory size to ensure logs were not consuming excessive disk space.

---

## Network Snapshot

### Command

```bash
ss -tulpn
```

### Observation

Verified listening ports and active services.

---

### Command

```bash
ping -c 4 google.com
```

### Observation

Network connectivity was successful with packet responses received.

---

## Logs Reviewed

### Command

```bash
journalctl -u ssh -n 50
```

### Observation

Reviewed recent SSH login and authentication events.

---

### Command

```bash
tail -n 50 /var/log/syslog
```

### Observation

Reviewed recent system log entries and found no critical errors.

---

## Quick Findings

* SSH service is active and running.
* CPU and memory utilization are healthy.
* Disk usage is within safe limits.
* Network connectivity is working correctly.
* No critical errors found in recent logs.

---

## If This Worsens

1. Restart SSH service and monitor logs:

   ```bash
   sudo systemctl restart ssh
   ```

2. Increase log inspection and review authentication failures:

   ```bash
   journalctl -u ssh -f
   ```

3. Collect deeper diagnostics using:

   ```bash
   strace
   top
   ss -tulpn
   ```

## Conclusion

This troubleshooting drill helped build a repeatable process for checking service health, resource usage, networking, and logs before taking corrective action.

