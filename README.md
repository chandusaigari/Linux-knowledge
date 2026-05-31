# ⚙️ Linux Commands — Job Ready (DevOps / SRE / Cloud)

![Linux](https://img.shields.io/badge/Linux-System%20Admin-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![DevOps](https://img.shields.io/badge/DevOps-Production%20Ready-0A66C2?style=for-the-badge&logo=amazon-aws&logoColor=white)
![SRE](https://img.shields.io/badge/SRE-Incident%20Focused-critical?style=for-the-badge)
![Level](https://img.shields.io/badge/Level-Interview%20Ready-success?style=for-the-badge)

---

## 🚀 Overview
Production-focused Linux command reference for DevOps, SRE, and Cloud troubleshooting.

Focus:
- Debug production issues
- Handle incidents
- Pass interviews

---

## 📌 System & Basic Info
```
uname -a        # shows kernel + OS version (first check in any server issue)
uptime          # system load + running time (detect overload quickly)
hostname        # identifies machine in network
whoami          # shows current logged-in user (permission debugging)
id              # user + group IDs (access control check)
lscpu           # CPU details (cores, architecture)
lsblk           # disk partitions and storage devices
```


**⚡ Process Management**
```
ps aux          # shows all running processes (system snapshot)
top             # real-time CPU/memory usage (live monitoring)
htop            # improved version of top (interactive debugging)
pstree          # shows process hierarchy (parent-child issues)
pidof <process> # finds process ID by name
kill <PID>      # sends SIGTERM (graceful shutdown)
kill -9 <PID>   # force kill (SIGKILL, last option)
pkill <name>    # kill process by name (fast termination)
```
**🧠 Memory & CPU Debugging**
```
free -h               # shows RAM usage (memory pressure check)
vmstat 1              # CPU + memory + IO stats every second
iostat -xz 1          # disk IO bottleneck detection
top -o %CPU           # sort processes by CPU usage
top -o %MEM           # sort processes by memory usage
dmesg | grep -i oom   # detects out-of-memory kills (critical issue)
```
**💽 Disk & Storage**
```
df -h                 # disk space usage (partition-level check)
df -i                 # inode usage (file exhaustion issue)
du -sh *              # folder sizes (find heavy directories)
lsblk                 # shows disks and mount points
find / -size +500M    # finds large files causing disk issues
```
**📁 File Operations**
```
ls -la               # lists all files with permissions
cd                   # change directory
cp                   # copy files or folders
mv                   # move or rename files
rm -rf               # force delete (dangerous in production)
cat                  # display full file content
less                 # scroll large files safely
head                 # first lines of file
tail -f file         # live log monitoring (critical in debugging)
find / -name <file>  # search file by name
grep -r "text" .     # search text inside files recursively
```

**🔐 Permissions & Ownership**
```
chmod 755 file                 # sets read/write/execute permissions
chmod -R 755 dir              # recursive permission change
chown user:group file         # changes file ownership
getfacl file                  # views ACL permissions (advanced control)
setfacl -m u:user:rwx file    # modifies ACL permissions
```

**👥 Users & Groups**
```
useradd <user>                 # create new system user
usermod -aG <group> <user>     # add user to group
passwd <user>                  # set user password
who                            # shows logged-in users
w                              # active sessions + system load
last                           # login history (audit trail)
```
**🌐 Networking**
```
ip a                  # shows IP addresses (network identity)
ip r                  # routing table (network path)
ping <host>           # checks connectivity
curl -I <url>         # checks HTTP response headers
ss -tulnp             # shows open ports and services
netstat -tulnp        # legacy version of ss
lsof -i               # shows network connections used by processes
nc -zv <host> <port>  # tests if port is open
```

**📜 Logs & Debugging**
```
journalctl -xe              # system-wide error logs
journalctl -u <service>     # logs for specific service
dmesg -T                    # kernel logs with timestamps
tail -f /var/log/syslog    # live system logs
grep -i error /var/log/*    # searches errors in logs
```

**⚙️ Systemd / Services**
```
systemctl status <service>    # checks service health
systemctl restart <service>   # restarts service (fix deploy issues)
systemctl enable <service>    # enables service at boot
systemctl --failed            # shows failed services
```
**🔑 SSH & Remote Access**
```
ssh user@host                     # remote login to server
ssh -i key.pem user@host          # login using private key
scp file user@host:/path          # secure file transfer
rsync -avz file user@host:/path   # efficient file sync
```

**🐳 Docker Essentials**
```
docker ps                 # running containers (service view)
docker images             # list available images
docker run <image>        # start container
docker logs <container>   # check container logs
docker exec -it <container> bash  # enter container shell
docker system prune       # clean unused resources
```

**🚨 Incident Debug Kit (CRITICAL)**
```

Used during real production outages:

uptime              # checks system load spikes
top                 # identifies CPU/memory hogs
free -h             # checks memory exhaustion
df -h               # checks disk full issues
ps aux              # process snapshot of system
ss -tulnp           # checks ports/services
systemctl status <service>  # service health check
journalctl -xe      # system failure logs
dmesg               # kernel-level errors
curl -I localhost   # checks local service health
```

**🧩 Interview Signal Map**
```
CPU spike → top, vmstat
Memory leak → free, dmesg
Service crash → systemctl, journalctl
Network failure → ss, curl, ping
Disk full → df, du
Process issue → ps, kill
```
Commit at 2026-04-07T14:27:19.181036
Commit at 2026-02-25T07:18:15.351879
Commit at 2026-03-17T15:43:28.514914
Commit at 2025-07-12T10:24:56.654074
Commit at 2026-01-06T00:53:18.795565
Commit at 2025-11-20T01:17:03.924540
Commit at 2026-01-31T13:02:16.081699
Commit at 2025-08-26T01:18:39.250823
Commit at 2026-01-24T23:13:25.400449
Commit at 2026-03-19T07:17:52.538685
Commit at 2025-09-02T01:22:28.688544
Commit at 2025-10-30T00:22:14.824720
Commit at 2025-11-15T20:52:03.333081
Commit at 2025-11-08T00:48:00.483346
Commit at 2026-05-21T23:16:33.617877
Commit at 2025-08-14T07:59:01.751579
Commit at 2025-12-05T02:05:45.894495
Commit at 2025-10-30T03:05:19.030657
Commit at 2025-06-16T17:46:11.170468
Commit at 2025-12-05T18:32:47.305341
Commit at 2025-09-30T19:54:51.457304
Commit at 2025-08-27T04:04:21.587139
Commit at 2026-04-27T18:44:36.719278
Commit at 2025-06-05T11:02:52.847605
Commit at 2025-06-26T06:00:30.996196
Commit at 2025-10-06T02:48:22.119706
Commit at 2026-05-18T23:08:36.250238
