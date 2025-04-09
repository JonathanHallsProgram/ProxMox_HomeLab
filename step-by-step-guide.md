# Detailed Installation Guide: Proxmox VE on HP ProDesk 400 G4 SFF

This guide details each step to install Proxmox Virtual Environment 7.x on your HP ProDesk 400 G4 Desktop Small Form Factor, equipped with an Intel Core i5-6500 processor, 8GB DDR4, and a 240GB SSD.

---

## [Hardware Specifications](#hardware-specifications)

- **Model:** HP ProDesk 400 G4 Desktop Small Form Factor  
- **Processor:** Intel Quad-Core i5-6500 (up to 3.6 GHz)  
- **Memory:** 8GB DDR4  
- **Storage:** 240GB SSD  
- **Graphics:** VGA, DP  
- **Pre-installed OS:** Windows 10 Pro 64-bit (to be replaced by Proxmox VE)

---

## [Pre-Installation Steps](#pre-installation-steps)

1. **Backup Your Data:**  
   Ensure that you have a backup of any important data since the installation will overwrite the existing OS.

### [Download Proxmox VE ISO](#download-proxmox-ve-iso)
   - Visit the [Proxmox Download Page](https://www.proxmox.com/en/downloads/category/iso-images-pve) and download the latest Proxmox VE 7.x ISO image.

### [Create a Bootable USB Drive](#create-a-bootable-usb-drive)
   - **For Windows Users:**  
     Use [Rufus](https://rufus.ie) to create a bootable USB drive:
     - Open Rufus.
     - Select your USB drive.
     - Choose the downloaded Proxmox ISO.
     - Click “Start” and wait for the process to complete.
   - **For Linux Users:**  
     Use the following command (replace `/dev/sdX` with your USB device identifier):
     ```bash
     sudo dd if=proxmox-ve.iso of=/dev/sdX bs=4M status=progress && sync
     ```

---

## [Entering the BIOS](#entering-the-bios)

1. **Access the BIOS:**  
   - Restart your HP ProDesk 400 G4.
   - As soon as the system begins to boot, press the `Esc` key repeatedly to access the startup menu.
   - Then, press the `F10` key to enter the BIOS setup.

2. **Adjust Boot Priority:**  
   - Navigate to the **Boot Options** menu.
   - Set your bootable USB drive as the first boot device.
   - Save the changes and exit the BIOS setup.

3. **Enable Virtualization (VT-x):**  
   - Within the BIOS, go to the **Advanced** or **System Configuration** section.
   - Locate the virtualization settings (often labeled as VT-x or Virtualization Technology) and enable them.

4. **Disable Secure Boot:**  
   - In the BIOS, find the **Secure Boot** option (usually under the **Boot** or **Security** tab).
   - Set Secure Boot to **Disabled**. This is required to allow the installation of non-Windows operating systems like Proxmox.

---

## [Installing Proxmox VE](#installing-proxmox-ve)

1. **Boot from the USB Drive:**  
   - With the bootable USB inserted, restart the system.
   - The system should now boot from the USB drive and display the Proxmox VE installer menu.

2. **Start the Installation Process:**  
   - Select **"Install Proxmox VE"** from the installer menu.

3. **Accept the License Agreement:**  
   - Review and accept the license agreement to continue with the installation.

4. **Select the Installation Drive:**  
   - When prompted, select the 240GB SSD as the target drive for installing Proxmox.
   - **Warning:** Ensure you have selected the correct drive as all data on it will be erased.

5. **Configure System Settings:**  
   - Set your location, time zone, and keyboard layout to match your preferences.
   - This ensures the Proxmox system clock and regional settings are correct.

6. **Set Administrative Credentials:**  
   - Provide a strong password for the Proxmox web interface.
   - Enter a valid email address for system notifications and administrative alerts.

7. **Network Configuration:**  
   - Configure the network settings:
     - If using DHCP, the installer may automatically assign an IP address.
     - For static configurations, manually enter the appropriate IP address, subnet mask, gateway, and DNS settings.

---

## [Post-Installation Setup](#post-installation-setup)

1. **Reboot the System:**  
   - After the installation completes, remove the USB drive.
   - Reboot the machine.

2. **Access the Proxmox Web Interface:**  
   - From another computer, open a web browser.
   - Navigate to:
     ```
     https://<your-proxmox-ip>:8006
     ```
   - If you receive any certificate warnings, proceed by accepting them (since it's a self-signed certificate).

3. **Finalize the Setup:**  
   - Through the web interface, complete the initial configuration:
     - Configure storage options.
     - Set up networking (if further adjustments are necessary).
     - Create your first virtual machine (VM) or Linux Container (LXC).
   - Explore additional Proxmox settings for optimal performance and security.

---

## [Final Notes](#final-notes)

- **BIOS Considerations:** The steps provided assume use of UEFI mode. If you choose Legacy BIOS mode, ensure the boot settings match accordingly.
- **Hardware Limitations:** With 8GB of RAM and a 240GB SSD, plan your virtual machine usage accordingly, as these resources are modest for a production environment.
- **Updates & Maintenance:** Regularly check the [Proxmox Community Forum](https://forum.proxmox.com/) and [official documentation](https://pve.proxmox.com/wiki/Main_Page) for updates and best practices.

---

By following these detailed instructions, you should be able to successfully install and configure Proxmox VE on your HP ProDesk 400 G4 SFF desktop system.
