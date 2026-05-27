# ⚙️ Linux Commands — Job Ready (DevOps / SRE / Cloud)

![Linux](https://img.shields.io/badge/Linux-System%20Admin-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![DevOps](https://img.shields.io/badge/DevOps-Production%20Ready-0A66C2?style=for-the-badge&logo=amazon-aws&logoColor=white)
![SRE](https://img.shields.io/badge/SRE-Incident%20Focused-critical?style=for-the-badge)
![Level](https://img.shields.io/badge/Level-Interview%20Ready-success?style=for-the-badge)

---

## 🚀 Overview
Production-focused Linux command reference for:
- DevOps interviews
- SRE incident debugging
- Cloud infrastructure troubleshooting

> Focus: real-world execution, not theory

---

## 📌 System & Basic Info
```bash
uname -a        # kernel + OS details (first command in any debug)
uptime          # system load + how long system has been running
hostname        # machine identity in network
whoami          # current logged-in user
id              # user ID + group ID (permissions check)
lscpu           # CPU architecture + cores (capacity check)
lsblk           # disk layout + attached storage devices
⚡ Process Management
ps aux          # list all running processes (baseline process view)
top             # live CPU + memory usage (real-time monitoring)
htop            # improved interactive process viewer (if installed)
pstree          # parent-child process hierarchy (useful for debugging forks)
pidof <process> # get PID of a running process
kill <PID>      # graceful process termination (SIGTERM)
kill -9 <PID>   # force kill (SIGKILL - use only if needed)
pkill <name>    # kill process by name (faster targeting)
🧠 Memory & CPU Debugging
free -h               # RAM usage in human-readable format
vmstat 1              # CPU, memory, IO stats every second
iostat -xz 1          # disk + CPU IO bottleneck detection
top -o %CPU           # sort processes by CPU usage
top -o %MEM           # sort processes by memory usage
dmesg | grep -i oom   # detect Out-Of-Memory kills (critical issue)
💽 Disk & Storage
df -h                 # disk space usage (partition-level)
df -i                 # inode usage (file limit check)
du -sh *              # folder sizes (find heavy directories)
lsblk                 # block devices + mount points
find / -size +500M    # locate large files causing disk pressure
📁 File Operations
ls -la               # detailed file listing (permissions + hidden files)
cd                   # navigate directories
cp                   # copy files/directories
mv                   # move or rename files
rm -rf               # force delete (dangerous in production)
cat                  # display full file content
less                 # paginated file viewing (safe for logs)
head                 # first lines of file
tail -f file         # real-time log streaming (critical in debugging)
find / -name <file>  # search file by name
grep -r "text" .     # search text inside files recursively
🔐 Permissions & Ownership
chmod 755 file                 # rwx for owner, rx for others
chmod -R 755 dir              # recursive permission change
chown user:group file         # change ownership
getfacl file                  # view ACL permissions (advanced)
setfacl -m u:user:rwx file    # modify ACL permissions
👥 Users & Groups
useradd <user>                 # create new user
usermod -aG <group> <user>     # add user to group
passwd <user>                  # set/reset password
who                            # logged-in users
w                              # active sessions + load
last                           # login history (audit check)
🌐 Networking
ip a                  # show IP addresses (network identity)
ip r                  # routing table (network path)
ping <host>           # connectivity test (ICMP check)
curl -I <url>         # HTTP header check (service health)
ss -tulnp             # open ports + listening services
netstat -tulnp        # legacy port checker (older systems)
lsof -i               # processes using network sockets
nc -zv <host> <port>  # test port connectivity
📜 Logs & Debugging
journalctl -xe              # system-wide error logs
journalctl -u <service>     # logs for specific service
dmesg -T                    # kernel logs with timestamps
tail -f /var/log/syslog    # live system logs
grep -i error /var/log/*    # scan logs for errors
⚙️ Systemd / Services
systemctl status <service>    # check service health
systemctl restart <service>   # restart service (fix deploy issues)
systemctl enable <service>    # enable auto-start on boot
systemctl --failed            # list failed services (outage detection)
🔑 SSH & Remote Access
ssh user@host                     # remote login
ssh -i key.pem user@host          # key-based authentication
scp file user@host:/path          # secure file copy
rsync -avz file user@host:/path   # efficient sync (production preferred)
🐳 Docker Essentials
docker ps                 # running containers (service layer view)
docker images             # available images
docker run <image>        # start container
docker logs <container>   # container logs (debug runtime issues)
docker exec -it <container> bash  # enter container shell
docker system prune       # cleanup unused resources
🚨 Incident Debug Kit (CRITICAL)

Used during production outages.

uptime              # check system load spikes
top                 # identify resource-heavy process
free -h             # memory exhaustion check
df -h               # disk full issues
ps aux              # process snapshot
ss -tulnp           # port/service check
systemctl status <service>  # service health
journalctl -xe      # system error logs
dmesg               # kernel-level failures
curl -I localhost   # local service health check
🧩 Interview Signal Map
CPU spike → top, vmstat
Memory leak → free -h, dmesg
Service crash → systemctl, journalctl
Network failure → ss, curl, ping
Disk full → df, du
Process issue → ps, kill
