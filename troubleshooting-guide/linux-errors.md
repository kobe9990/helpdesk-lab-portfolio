# 🐧 Linux Errors — Troubleshooting Guide

---

## Error 01: Kernel Panic
**Symptoms:**
- System freezes with "Kernel panic - not syncing" message
- Cannot boot into OS
- Screen becomes unresponsive

**Common Causes:**
- Corrupt kernel files
- Incompatible hardware driver
- Failed system update

**Steps to Fix:**
1. Reboot and hold SHIFT to open GRUB menu
2. Select "Advanced options" → boot into older kernel version
3. Once booted run: `sudo apt update && sudo apt upgrade`
4. Reinstall kernel: `sudo apt install --reinstall linux-generic`
5. Reboot normally

**Resolution:** Booting into an older kernel and reinstalling resolves most kernel panics.

---

## Error 02: GRUB Rescue Prompt
**Symptoms:**
- On boot, only sees `grub rescue>` prompt
- Cannot load operating system
- Happens after disk changes or failed updates

**Steps to Fix:**
1. Type `ls` to list available partitions
2. Find your Linux partition (e.g. (hd0,1))
3. Run:
   - `set root=(hd0,1)`
   - `set prefix=(hd0,1)/boot/grub`
   - `insmod normal`
   - `normal`
4. Once booted run: `sudo update-grub` and `sudo grub-install /dev/sda`

**Resolution:** Manually setting the root and reinstalling GRUB fixes the boot issue.

---

## Error 03: Permission Denied
**Symptoms:**
- Terminal returns "Permission denied" when running commands
- Cannot access or edit certain files
- User lacks admin rights

**Common Causes:**
- Running command without sudo
- File owned by different user
- Incorrect file permissions set

**Steps to Fix:**
1. Try running command with `sudo` prefix
2. Check file permissions: `ls -la filename`
3. Change ownership: `sudo chown username:username filename`
4. Change permissions: `sudo chmod 755 filename`

**Resolution:** Adding sudo or correcting file ownership resolves permission errors.

---

## Error 04: Network Interface Not Found
**Symptoms:**
- No internet connection
- `ifconfig` or `ip a` shows no active interfaces
- Network adapter not detected

**Steps to Fix:**
1. Run `ip link show` to list all interfaces
2. Bring interface up: `sudo ip link set eth0 up`
3. Check if driver is loaded: `lspci -k`
4. Restart network service: `sudo systemctl restart networking`
5. If WiFi: `sudo systemctl restart NetworkManager`

**Resolution:** Restarting the network service or bringing the interface up manually resolves connectivity.

---

## Error 05: SSH Connection Refused
**Symptoms:**
- Terminal returns "Connection refused" on SSH attempt
- Cannot remotely access machine
- Port 22 not responding

**Common Causes:**
- SSH service not running
- Firewall blocking port 22
- Wrong IP address or port

**Steps to Fix:**
1. On target machine check SSH status: `sudo systemctl status ssh`
2. Start SSH if not running: `sudo systemctl start ssh`
3. Enable on startup: `sudo systemctl enable ssh`
4. Check firewall: `sudo ufw allow 22` and `sudo ufw reload`
5. Verify correct IP with: `ip a`

**Resolution:** Starting the SSH service and opening port 22 in the firewall resolves connection issues.
