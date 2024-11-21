# Single-Drive NAS Setup with TrueNAS

## Purpose
This repository documents the setup and configuration of a personal NAS using TrueNAS with a single-drive setup. Ideal for testing, learning, or minimal use cases.

## System Details
- **System Type:** Desktop
- **OS:** TrueNAS 13.0
- **Storage:** Single 1TB drive (no partitions)
- **Network:** Ethernet connection for reliable access

## Objectives
- Set up a simple NAS for file sharing and backups.
- Explore the functionality of TrueNAS on limited hardware.

## Contents
- [Proxmox Setup Guide](docs/proxmox-setup-guide.md)
- [Troubleshooting](docs/troubleshooting.md)
- [Installing TrueNAS on Proxmox](docs/truenas-on-proxmox-guide.md)
- Example configurations in the `configs/` directory.

## Setup Instructions
1. Install TrueNAS on the single drive.
2. Configure network shares via SMB.
3. Set up user accounts and permissions.
4. Regularly back up data to external devices.

## Quick Start
1. Follow the [Proxmox Setup Guide](docs/proxmox-setup-guide.md).
2. Use the provided configurations and tips to customize your installation.

## Limitations
- No RAID or redundancy; data loss is possible in the event of drive failure.
- Designed for learning or non-critical data storage.

## Recommendations
- Back up data regularly.
- Consider adding additional drives for redundancy in production environments.

---

Feel free to adjust based on your specific setup!
