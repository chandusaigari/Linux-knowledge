<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Linux Commands — Job Ready</title>

<style>
    body {
        font-family: Arial, sans-serif;
        background: #0b0f19;
        color: #e6e6e6;
        margin: 0;
        padding: 0;
        line-height: 1.6;
    }

    .container {
        width: 90%;
        max-width: 1100px;
        margin: auto;
        padding: 20px;
    }

    h1 {
        text-align: center;
        color: #facc15;
        margin-bottom: 5px;
    }

    .badges {
        text-align: center;
        margin-bottom: 20px;
    }

    .badge {
        display: inline-block;
        padding: 6px 10px;
        margin: 3px;
        border-radius: 5px;
        font-size: 12px;
        background: #1f2937;
        color: white;
    }

    h2 {
        color: #38bdf8;
        margin-top: 30px;
        border-left: 4px solid #38bdf8;
        padding-left: 10px;
    }

    pre {
        background: #111827;
        padding: 15px;
        border-radius: 8px;
        overflow-x: auto;
    }

    code {
        color: #22c55e;
    }

    .section {
        margin-bottom: 30px;
    }

    .note {
        background: #1e293b;
        padding: 10px;
        border-left: 4px solid #f59e0b;
        margin-top: 10px;
    }

    ul {
        padding-left: 20px;
    }

</style>
</head>

<body>

<div class="container">

    <h1>⚙️ Linux Commands — Job Ready</h1>

    <div class="badges">
        <span class="badge">Linux</span>
        <span class="badge">DevOps</span>
        <span class="badge">SRE</span>
        <span class="badge">Interview Ready</span>
    </div>

    <div class="note">
        Production-focused Linux command reference for DevOps, SRE, and Cloud debugging.
    </div>

    <!-- SYSTEM -->
    <div class="section">
        <h2>📌 System & Basic Info</h2>
        <pre><code>uname -a        # kernel + OS details
uptime          # system load + uptime
hostname        # system name
whoami          # current user
id              # user info
lscpu           # CPU details
lsblk           # disk structure</code></pre>
    </div>

    <!-- PROCESS -->
    <div class="section">
        <h2>⚡ Process Management</h2>
        <pre><code>ps aux
top
htop
pstree
pidof &lt;process&gt;
kill &lt;PID&gt;
kill -9 &lt;PID&gt;
pkill &lt;name&gt;</code></pre>
    </div>

    <!-- MEMORY -->
    <div class="section">
        <h2>🧠 Memory & CPU Debugging</h2>
        <pre><code>free -h
vmstat 1
iostat -xz 1
top -o %CPU
top -o %MEM
dmesg | grep -i oom</code></pre>
    </div>

    <!-- DISK -->
    <div class="section">
        <h2>💽 Disk & Storage</h2>
        <pre><code>df -h
df -i
du -sh *
lsblk
find / -size +500M</code></pre>
    </div>

    <!-- FILES -->
    <div class="section">
        <h2>📁 File Operations</h2>
        <pre><code>ls -la
cd
cp
mv
rm -rf
cat
less
head
tail -f file
find / -name &lt;file&gt;
grep -r "text" .</code></pre>
    </div>

    <!-- PERMISSIONS -->
    <div class="section">
        <h2>🔐 Permissions & Ownership</h2>
        <pre><code>chmod 755 file
chmod -R 755 dir
chown user:group file
getfacl file
setfacl -m u:user:rwx file</code></pre>
    </div>

    <!-- USERS -->
    <div class="section">
        <h2>👥 Users & Groups</h2>
        <pre><code>useradd &lt;user&gt;
usermod -aG &lt;group&gt; &lt;user&gt;
passwd &lt;user&gt;
who
w
last</code></pre>
    </div>

    <!-- NETWORK -->
    <div class="section">
        <h2>🌐 Networking</h2>
        <pre><code>ip a
ip r
ping &lt;host&gt;
curl -I &lt;url&gt;
ss -tulnp
netstat -tulnp
lsof -i
nc -zv &lt;host&gt; &lt;port&gt;</code></pre>
    </div>

    <!-- LOGS -->
    <div class="section">
        <h2>📜 Logs & Debugging</h2>
        <pre><code>journalctl -xe
journalctl -u &lt;service&gt;
dmesg -T
tail -f /var/log/syslog
grep -i error /var/log/*</code></pre>
    </div>

    <!-- SYSTEMD -->
    <div class="section">
        <h2>⚙️ Systemd / Services</h2>
        <pre><code>systemctl status &lt;service&gt;
systemctl restart &lt;service&gt;
systemctl enable &lt;service&gt;
systemctl --failed</code></pre>
    </div>

    <!-- SSH -->
    <div class="section">
        <h2>🔑 SSH & Remote Access</h2>
        <pre><code>ssh user@host
ssh -i key.pem user@host
scp file user@host:/path
rsync -avz file user@host:/path</code></pre>
    </div>

    <!-- DOCKER -->
    <div class="section">
        <h2>🐳 Docker Essentials</h2>
        <pre><code>docker ps
docker images
docker run &lt;image&gt;
docker logs &lt;container&gt;
docker exec -it &lt;container&gt; bash
docker system prune</code></pre>
    </div>

    <!-- INCIDENT -->
    <div class="section">
        <h2>🚨 Incident Debug Kit</h2>
        <pre><code>uptime
top
free -h
df -h
ps aux
ss -tulnp
systemctl status &lt;service&gt;
journalctl -xe
dmesg
curl -I localhost</code></pre>
    </div>

    <!-- MAP -->
    <div class="section">
        <h2>🧩 Interview Signal Map</h2>
        <ul>
            <li>CPU spike → top, vmstat</li>
            <li>Memory leak → free, dmesg</li>
            <li>Service crash → systemctl, journalctl</li>
            <li>Network issue → ss, curl, ping</li>
            <li>Disk full → df, du</li>
            <li>Process issue → ps, kill</li>
        </ul>
    </div>

</div>

</body>
</html>
