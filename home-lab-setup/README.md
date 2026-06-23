# 🏠 Home Lab Setup

## Overview
A virtualized home lab environment built to simulate a small office IT setup.
Used for hands-on practice with hardware, OS configuration, and networking concepts
covered in the CompTIA A+ certification.

## Host Machine
| Component | Details |
|---|---|
| OS | macOS |
| Virtualization Software | VirtualBox |
| RAM Allocated to VMs | 4GB per VM |
| Storage | 50GB per VM |

## Virtual Machines

### 💻 VM 1 — Windows 11
| Setting | Details |
|---|---|
| OS | Windows 11 Pro |
| RAM | 4GB |
| Storage | 50GB |
| Purpose | Simulate end-user workstation for help desk troubleshooting |

**Tasks Practiced:**
- OS installation and initial setup
- User account creation and management
- Windows Update configuration
- Driver installation and troubleshooting
- Network adapter configuration

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
- SSH configuration and remote access
- Network interface troubleshooting
- Package installation via apt

## Network Setup
- Both VMs connected via VirtualBox internal network
- Simulates a small office LAN environment
- practiced pinging between VMs to verify connectivity

## Tools Used
- VirtualBox (virtualization)
- Windows 11 (end-user OS)
- Ubuntu 22.04 (Linux server OS)
- draw.io (network diagrams)

## Skills Demonstrated
- Hardware and OS configuration
- Virtualization setup and management
- Network configuration between machines
- Cross-platform troubleshooting (Windows + Linux)

## Status
✅ Complete
