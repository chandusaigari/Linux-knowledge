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
Commit at 2025-06-01T18:06:50.747269
Commit at 2026-03-13T01:23:26.891155
Commit at 2026-03-10T08:21:09.022135
Commit at 2026-02-03T22:32:50.157661
Commit at 2026-05-14T13:38:51.286633
Commit at 2026-03-03T00:44:16.411832
Commit at 2025-09-29T05:47:15.543053
Commit at 2026-05-21T14:41:08.673141
Commit at 2025-09-29T11:12:14.838579
Commit at 2025-07-16T01:53:50.967819
Commit at 2025-08-14T23:33:02.099011
Commit at 2026-02-17T17:06:35.228088
Commit at 2026-04-09T19:14:58.361022
Commit at 2025-12-09T01:18:57.497746
Commit at 2025-11-16T08:18:18.631289
Commit at 2025-08-06T04:45:19.338463
Commit at 2026-04-23T22:50:52.485147
Commit at 2026-04-27T15:46:24.616356
Commit at 2026-04-07T04:52:37.747152
Commit at 2025-06-30T21:46:36.876270
Commit at 2026-02-01T09:15:40.023859
Commit at 2025-06-04T11:03:36.172495
Commit at 2025-10-21T11:33:21.302879
Commit at 2026-03-05T21:24:38.445801
Commit at 2026-04-04T15:07:17.578610
Commit at 2026-02-21T19:36:57.711242
Commit at 2026-04-10T13:05:48.836440
Commit at 2025-09-02T21:01:02.965328
Commit at 2026-04-04T15:14:34.125783
Commit at 2026-04-24T14:00:24.256487
Commit at 2025-07-21T23:44:57.738096
Commit at 2026-04-28T10:07:51.888330
Commit at 2026-04-05T23:56:40.020112
Commit at 2026-04-11T16:46:47.139430
Commit at 2025-08-27T14:52:26.259958
Commit at 2026-01-08T21:58:45.394603
Commit at 2025-12-09T21:49:43.522680
Commit at 2026-02-28T00:51:15.642900
Commit at 2025-07-15T18:35:16.826003
Commit at 2025-07-02T17:22:05.963542
Commit at 2025-10-04T20:10:55.088614
Commit at 2025-12-11T11:07:25.215551
Commit at 2025-08-24T20:41:12.336512
Commit at 2026-01-12T14:30:44.457141
Commit at 2025-06-05T16:03:00.580814
Commit at 2025-07-11T14:33:38.709272
Commit at 2025-07-13T17:46:44.853454
Commit at 2026-01-07T09:16:51.982579
Commit at 2025-11-24T17:08:24.104565
Commit at 2025-10-16T22:54:15.229859
Commit at 2026-03-05T20:20:25.865723
Commit at 2025-12-15T17:36:52.005524
Commit at 2025-08-20T10:33:51.144142
Commit at 2025-06-03T21:26:49.285473
Commit at 2026-05-24T13:13:33.416114
Commit at 2026-05-22T01:37:27.543208
Commit at 2025-06-14T06:18:16.668288
Commit at 2026-03-24T23:22:53.802080
Commit at 2025-09-20T04:34:32.929143
Commit at 2025-11-22T21:32:01.061446
Commit at 2025-08-25T11:34:06.350435
Commit at 2025-09-11T22:10:51.478633
Commit at 2025-11-01T14:40:39.608310
Commit at 2026-01-24T23:47:04.737031
Commit at 2026-03-02T03:15:01.862014
Commit at 2025-08-21T04:35:18.992895
Commit at 2026-05-18T19:51:44.122564
Commit at 2025-09-14T02:00:19.275522
Commit at 2025-12-30T22:22:27.404269
Commit at 2025-08-11T21:22:33.529465
Commit at 2026-04-05T17:32:37.953146
Commit at 2025-09-30T03:54:32.087475
Commit at 2026-04-14T03:26:35.218488
Commit at 2026-02-14T03:59:05.340761
Commit at 2025-06-09T04:13:28.463760
Commit at 2025-10-05T08:26:57.597795
Commit at 2026-03-09T01:20:02.724942
Commit at 2026-04-03T18:39:04.847941
Commit at 2025-08-27T04:58:11.974040
Commit at 2025-10-30T06:10:56.103731
Commit at 2026-05-14T12:51:39.257136
Commit at 2025-09-07T15:24:35.377202
Commit at 2026-05-24T02:34:04.498904
Commit at 2025-09-24T15:11:42.628630
Commit at 2025-08-01T05:36:49.756375
Commit at 2026-02-09T12:38:57.886339
Commit at 2025-07-16T16:04:53.011991
Commit at 2026-01-07T20:10:14.166793
Commit at 2025-06-02T21:22:50.299645
Commit at 2025-07-30T22:55:44.422884
Commit at 2026-02-28T21:23:14.217036
Commit at 2025-08-21T00:22:51.580299
Commit at 2026-05-30T15:07:41.969618
Commit at 2025-11-16T20:02:33.336394
Commit at 2025-06-03T05:12:26.731665
Commit at 2025-08-29T04:27:18.110769
Commit at 2026-02-26T01:40:15.635155
Commit at 2026-05-28T21:55:58.007634
Commit at 2025-10-03T20:02:10.374253
Commit at 2025-09-12T14:02:22.797970
Commit at 2025-07-12T21:09:13.215766
Commit at 2025-11-30T00:43:12.578093
Commit at 2025-06-12T03:39:46.923113
Commit at 2025-08-17T08:51:46.284450
Commit at 2026-01-09T01:29:57.672433
Commit at 2026-04-07T05:46:03.087112
Commit at 2025-10-30T07:50:20.509217
Commit at 2026-04-12T03:09:50.852796
Commit at 2026-05-26T16:20:35.263061
Commit at 2025-08-18T01:15:21.676024
Commit at 2025-06-07T00:51:57.584226
Commit at 2025-08-28T00:35:18.939253
Commit at 2025-09-24T19:44:38.329211
Commit at 2025-06-09T20:16:37.701724
Commit at 2026-03-17T06:44:04.040003
Commit at 2026-03-10T16:33:28.442211
Commit at 2025-07-19T20:02:11.820516
Commit at 2026-01-21T06:31:59.270245
Commit at 2026-03-07T08:30:10.685720
Commit at 2025-08-16T13:30:46.003318
Commit at 2025-09-19T03:25:02.384668
Commit at 2026-03-18T17:50:06.772670
Commit at 2025-08-15T09:05:22.268857
Commit at 2025-12-25T14:30:09.680005
Commit at 2025-08-02T00:27:04.284304
Commit at 2025-07-18T14:36:44.715480
Commit at 2025-10-23T01:10:49.153894
Commit at 2025-11-16T05:25:14.535948
Commit at 2025-10-07T13:26:55.856863
Commit at 2025-06-14T23:39:55.380159
Commit at 2026-03-09T03:41:45.239864
