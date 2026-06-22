# 🪟 Windows Errors — Troubleshooting Guide

---

## Error 01: Blue Screen of Death (BSOD)
**Error Code:** 0x0000001A (MEMORY_MANAGEMENT)
**Symptoms:**
- System crashes with a blue screen
- Computer restarts automatically
- Error code displayed on screen

**Common Causes:**
- Faulty or incompatible RAM
- Corrupt system files
- Outdated or corrupt drivers

**Steps to Fix:**
1. Restart and boot into Safe Mode
2. Run `mdsched.exe` to test RAM
3. Open CMD as admin and run `sfc /scannow`
4. Check Event Viewer for related errors
5. Update or roll back recent drivers

**Resolution:** In most cases, running sfc /scannow repairs corrupt files and resolves the BSOD.

---

## Error 02: PC Won't Boot / No Bootable Device
**Symptoms:**
- Black screen on startup
- Message says "No bootable device found"
- System skips past OS loading screen

**Common Causes:**
- Boot order incorrect in BIOS
- Corrupt Master Boot Record (MBR)
- Failed hard drive

**Steps to Fix:**
1. Enter BIOS (F2, F12, or DEL on startup)
2. Check boot order — set HDD/SSD as first boot device
3. Boot from Windows installation media
4. Open CMD and run `bootrec /fixmbr` then `bootrec /fixboot`
5. Run `chkdsk /f /r` to check for drive errors

**Resolution:** Fixing the boot order in BIOS or repairing the MBR resolves this in most cases.

---

## Error 03: Windows Update Stuck or Failing
**Symptoms:**
- Update sits at 0% or loops repeatedly
- Error codes like 0x80070057 or 0x800f081f
- System unusable during failed update

**Common Causes:**
- Corrupt Windows Update cache
- Insufficient disk space
- Windows Update service not running

**Steps to Fix:**
1. Open Services and restart Windows Update service
2. Open CMD as admin and run:
   - `net stop wuauserv`
   - `del /f /q %windir%\SoftwareDistribution\*`
   - `net start wuauserv`
3. Free up disk space if under 10GB available
4. Run Windows Update Troubleshooter

**Resolution:** Clearing the update cache and restarting the service resolves most stuck updates.

---

## Error 04: User Account Locked Out
**Symptoms:**
- User cannot log in
- Message says account is locked or disabled
- Happens after multiple failed login attempts

**Common Causes:**
- Too many incorrect password attempts
- Cached credentials conflict
- Domain policy enforcement

**Steps to Fix:**
1. Log into admin account
2. Open Computer Management → Local Users and Groups
3. Right-click user → Properties → uncheck "Account is locked out"
4. Reset password if needed
5. Check Group Policy for lockout threshold settings

**Resolution:** Unlocking via admin panel and resetting credentials resolves the issue immediately.

---

## Error 05: Slow Performance / High CPU Usage
**Symptoms:**
- System runs sluggishly
- Fan running loudly
- Task Manager shows CPU at 90-100%

**Common Causes:**
- Background processes consuming resources
- Malware or virus activity
- Outdated drivers or too many startup programs

**Steps to Fix:**
1. Open Task Manager → identify high CPU processes
2. End unnecessary background tasks
3. Run Windows Defender full scan
4. Disable startup programs via Task Manager → Startup tab
5. Check for Windows updates and driver updates

**Resolution:** Disabling startup programs and removing malware resolves most performance issues.
