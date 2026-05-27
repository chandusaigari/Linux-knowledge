# Linux Commands — Job Ready (DevOps / SRE / Cloud)

> Production-focused Linux reference for interviews + real incident debugging.  
> Not theory. Not memorization. Execution-focused.

---

## 📌 Navigation
- [System Basics](#1-system--basic-info)
- [Process Management](#2-process-management)
- [Memory & CPU](#3-memory--cpu-debugging)
- [Disk & Storage](#4-disk--storage)
- [File Operations](#5-file-operations)
- [Permissions](#6-permissions--ownership)
- [Users](#7-users--groups)
- [Networking](#8-networking)
- [Logs](#10-logs--debugging)
- [Systemd](#11-systemd--services)
- [SSH](#12-ssh--remote-access)
- [Docker](#15-docker)
- [Incident Kit](#19-incident-debug-kit)

---

# 1. System & Basic Info

uname -a
uptime
hostname
whoami
id
lscpu
lsblk


---

# 2. Process Management
<details>
<summary>Expand</summary>


ps aux
top
htop
pstree
pidof <process>
kill <PID>
kill -9 <PID>
pkill <process>


</details>

---

# 3. Memory & CPU Debugging
<details>
<summary>Expand</summary>


free -h
vmstat 1
iostat -xz 1
top -o %CPU
top -o %MEM
dmesg | grep -i oom


</details>

---

# 4. Disk & Storage
<details>
<summary>Expand</summary>


df -h
df -i
du -sh *
lsblk
find / -size +500M


</details>

---

# 5. File Operations
<details>
<summary>Expand</summary>


ls -la
cd
cp
mv
rm -rf
cat
less
head
tail -f file
find / -name <file>
grep -r "text" .


</details>

---

# 6. Permissions & Ownership
<details>
<summary>Expand</summary>


chmod 755 file
chown user:group file
chmod -R 755 dir
getfacl file
setfacl -m u:user:rwx file


</details>

---

# 7. Users & Groups
<details>
<summary>Expand</summary>


useradd <user>
usermod -aG <group> <user>
passwd <user>
who
w
last


</details>

---

# 8. Networking
<details>
<summary>Expand</summary>


ip a
ip r
ping <host>
curl -I <url>
ss -tulnp
netstat -tulnp
lsof -i
nc -zv <host> <port>


</details>

---

# 10. Logs & Debugging
<details>
<summary>Expand</summary>


journalctl -xe
journalctl -u <service>
dmesg -T
tail -f /var/log/syslog
grep -i error /var/log/*


</details>

---

# 11. Systemd / Services
<details>
<summary>Expand</summary>


systemctl status <service>
systemctl restart <service>
systemctl enable <service>
systemctl --failed


</details>

---

# 12. SSH & Remote Access
<details>
<summary>Expand</summary>


ssh user@host
ssh -i key.pem user@host
scp file user@host:/path
rsync -avz file user@host:/path


</details>

---

# 15. Docker
<details>
<summary>Expand</summary>


docker ps
docker images
docker run <image>
docker logs <container>
docker exec -it <container> bash
docker system prune


</details>

---

# 19. Incident Debug Kit (MOST IMPORTANT)

uptime
top
free -h
df -h
ps aux
ss -tulnp
systemctl status <service>
journalctl -xe
dmesg
curl -I localhost
