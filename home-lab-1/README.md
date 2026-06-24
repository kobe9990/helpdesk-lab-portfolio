# 🏠 Home Lab Setup

## Overview
A virtualized home lab environment built on macOS using UTM, featuring Windows 11 and Ubuntu VMs. Designed to gain hands-on experience with operating system installation, configuration, network setup, and troubleshooting.

## Host Machine
| Component | Details |
|---|---|
| OS | macOS (M4 Chip) |
| Virtualization Software | UTM |
| RAM Allocated per VM | 4GB |
| Storage per VM | 64GB |

## Virtual Machines

### 💻 VM 1 — Windows 11 ARM
| Setting | Details |
|---|---|
| OS | Windows 11 (ARM version) |
| RAM | 4GB |
| Storage | 64GB |
| Purpose | Simulate end-user workstation for help desk troubleshooting |

**Tasks Practiced:**
- OS installation and initial setup
- User account creation and management
- Network adapter configuration
- Troubleshooting Windows errors

### 🐧 VM 2 — Ubuntu 22.04
| Setting | Details |
|---|---|
| OS | Ubuntu 22.04 LTS |
| RAM | 4GB |
| Storage | 50GB |
| Purpose | Simulate Linux server environment |

**Tasks Practiced:**
- Linux installation and terminal navigation
- File permissions and user management
- Network interface troubleshooting
- Package management via apt

## Tools Used
- UTM (virtualization on Apple Silicon)
- Windows 11 ARM (end-user OS)
- Ubuntu 22.04 (Linux server OS)
- macOS M4 (host machine)

## Status
✅ Complete — Both VMs running and documented
