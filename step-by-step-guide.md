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

## 4. Configure Dell BIOS Settings

1. **Access the BIOS:**  
   Restart your workstation and press `F2` (or your system’s designated key) to enter the BIOS setup.

2. **Adjust Boot Priority:**  
   Set your bootable USB drive as the first option in the boot order to ensure the system boots from it.

3. **Enable Virtualization:**  
   Locate the virtualization settings (commonly under "Advanced" or "CPU Configuration") and enable Intel VT-x or AMD-V.

4. **Disable Secure Boot:**  
   If Secure Boot is enabled, disable it to allow the installation of Proxmox.

   ## 5. Boot and Install Proxmox

1. **Start Installation:**  
   Boot from the USB drive and select "Install Proxmox VE" from the boot menu.

2. **License Agreement:**  
   Accept the license agreement to proceed.

3. **Select Installation Drive:**  
   Carefully choose the correct drive for the Proxmox installation.

4. **Configure System Settings:**  
   Set your location, time zone, and keyboard layout as required.

5. **Set Admin Credentials:**  
   Enter a strong password for the Proxmox web interface and provide a valid email for system notifications.

6. **Network Configuration:**  
   Configure the network settings to ensure proper connectivity.

   ## 6. Post-Installation Setup

1. **Reboot:**  
   After installation, remove the USB drive and reboot your system.

2. **Access the Web Interface:**  
   Open your browser and navigate to: https://<your-proxmox-ip>:8006

   If prompted, accept any certificate warnings.

3. **Further Configuration:**  
Finalize network and storage settings, and create your initial virtual machine or container through the web interface.
