# Step-by-Step Guide: Installing Proxmox on a Dell Workstation

## 1. Pre-Installation Checklist

- **Hardware Compatibility**: Verify that your Dell workstation supports hardware virtualization (VT-x/AMD-V) and meets the [Proxmox minimum requirements](https://www.proxmox.com/en/proxmox-ve/get-started).
- **Data Backup**: Backup important data before beginning the installation.
- **BIOS Configuration**: Ensure that virtualization is enabled in the BIOS. Disable Secure Boot if necessary.

## 2. Download the Proxmox VE ISO

- Visit the [Proxmox download page](https://www.proxmox.com/en/downloads/category/iso-images-pve) and download the latest ISO file.

## 3. Create a Bootable USB Drive

- **Windows Users**: Use a tool like [Rufus](https://rufus.ie) to write the ISO to a USB drive.
- **Linux Users**: Use the `dd` command:
  ```bash
  sudo dd if=proxmox-ve.iso of=/dev/sdX bs=4M status=progress && sync
