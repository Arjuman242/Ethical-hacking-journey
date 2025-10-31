
## Overview

Linux mein **services/daemons** background processes hote hain jo system ko chalane ya extra functionalities dene ke liye run karte hain. Modern distros mein `systemd` common init system hai — yeh boot pe PID 1 ke roop mein start hota hai.

Services do types ke hote hain:

* **System Services** — required during startup (kernel/hardware related). Example: `systemd`, `udevd`.
* **User-Installed Services** — optional, user-installed servers or background apps. Example: `apache2`, `sshd`.

## Goals (common tasks)

* Start / Stop / Restart a service
* Check status / logs
* Enable / Disable on boot
* Find processes (PID/PPID)
* Kill / signal a process
* Background / foreground processes

---

## systemctl — Basic usage

```bash
# Start, stop, restart
sudo systemctl start ssh
sudo systemctl stop ssh
sudo systemctl restart ssh

# Check status
systemctl status ssh

# Enable/disable on boot
sudo systemctl enable ssh
sudo systemctl disable ssh

# List services
systemctl list-units --type=service
```

Status output sample shows Service Unit, Active state, Main PID, CGroup, and recent log lines.

---

## Logs — journalctl

```bash
# Show logs for a unit (no pager so full output shows)
journalctl -u ssh.service --no-pager

# Follow logs live
journalctl -u apache2.service -f

# Show logs since a time
journalctl --since "2025-10-31 10:00"
```

Use `journalctl` to troubleshoot why a service failed to start.

---

## Processes, /proc, PID & PPID

* Har process ka ek **PID** hota hai; `init`/`systemd` ka PID 1 hota hai.
* Parent Process ID (PPID) batata hai kaun start kar chuka hai.
* `/proc/<PID>/` se process ki details milti hain.

Useful commands:

```bash
ps -aux | grep ssh
pstree -p    # process tree (agar installed ho)
cat /proc/<PID>/status
```

---

## Signals & kill

`kill -l` list karta hai available signals.
Common signals:

* `SIGHUP` (1): hangup / reload
* `SIGINT` (2): Ctrl-C
* `SIGTERM` (15): polite termination
* `SIGKILL` (9): force kill, cannot be caught

Examples:

```bash
# graceful terminate
kill -15 <PID>

# force kill
kill -9 <PID>

# send SIGHUP to reload config
kill -1 <PID>
```

You can use `pkill <name>` or `killall <name>` to target by process name.

---

## Backgrounding, foregrounding, jobs

```bash
# run command in background
ping -c 10 example.com &

# suspend current foreground job
[Ctrl+Z]
# list jobs
jobs
# put stopped job to background
bg %1
# bring job to foreground
fg %1
```

Notes:

* `&` starts process in background directly.
* Ctrl+Z sends `SIGTSTP` and suspends the process.
* Use `nohup command &` or `disown` if you want process to survive logout.

---

## Execute multiple commands

* Semicolon (`;`) — run sequentially, ignore previous exit status.
* Double ampersand (`&&`) — run next only if previous succeeded.
* Pipe (`|`) — connect stdout of left to stdin of right.

```bash
echo '1'; ls MISSING; echo '3'   # third runs despite error

echo '1' && ls MISSING && echo '3'  # stops on error

ps aux | grep ssh   # pipe example
```

---

## Practical examples / cheat-sheet

```bash
# Start and enable ssh
sudo systemctl start ssh
sudo systemctl enable ssh

# Check whether it's running
systemctl status ssh
ps -aux | grep ssh

# If service failed, inspect logs
journalctl -u ssh.service --no-pager

# Force kill a runaway process
sudo kill -9 <PID>

# Keep a long-running job after logout
nohup long_script.sh &
# or
long_script.sh &
disown
```

---

## Troubleshooting tips

* `systemctl status <unit>` often shows the immediate error.
* `journalctl -u <unit>` gives full logs and timestamps.
* Check permissions and unit file at `/lib/systemd/system/<unit>.service` or `/etc/systemd/system/`.
* For socket issues, ensure ports not already in use (`ss -tulpn` or `netstat -tulpn`).

---

#
