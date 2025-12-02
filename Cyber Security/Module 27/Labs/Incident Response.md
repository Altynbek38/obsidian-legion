
***

# Lab: Incident Response - System Info Gathering

**Objective:** Collect volatile system information and review security logs immediately after a security incident (before shutting down the system).

### 1. Collecting Volatile Information
**Goal:** Create a text report (`report.txt`) containing the system state. All commands are run as **root** (`sudo su`).

| Command | Purpose |
| :--- | :--- |
| `date >> report.txt` | Record start/end timestamps of the investigation. |
| `uname -a >> report.txt` | System/Kernel information. |
| `ifconfig -a >> report.txt` | Network interface configurations (IPs/MACs). |
| `netstat -ano >> report.txt` | **Network Statistics:** Open ports, established connections, and associated PIDs. |
| `ps axu >> report.txt` | **Processes:** Snapshot of all currently running processes and users. |
| `route -n >> report.txt` | Routing table (gateway information). |

**Execution Example:**
```bash
# 1. Elevate to root
sudo su

# 2. Create file and add timestamp
echo "Incident Report" > report.txt
date >> report.txt

# 3. Append system data (repeat for ifconfig, netstat, etc.)
echo "---System Info---" >> report.txt
uname -a >> report.txt

# 4. View final report
cat report.txt | less
```

### 2. Log Analysis
**Goal:** Review system logs for intrusion attempts.

| Log File | Path | Command to View | Description |
| :--- | :--- | :--- | :--- |
| **Auth Log** | `/var/log/auth.log` | `cat` or `less` | Logs authorization systems (sudo, ssh, cron). Shows who ran what commands. |
| **Bad Log** | `/var/log/btmp` | `last -f /var/log/btmp` | Binary file. Logs **failed** login attempts (brute force indicators). |
| **Who Log** | `/var/log/wtmp` | `last -f /var/log/wtmp` | Binary file. Logs **successful** login history and session duration. |

### Key Takeaways
*   **Order of Volatility:** Always capture RAM, processes, and network connections **before** analyzing disk files or powering off.
*   **Redirection:** Use `>>` to **append** to your report. Using `>` will overwrite existing data.
*   **Binary Logs:** `btmp` and `wtmp` cannot be read with `cat`; use the `last -f` command to parse them.