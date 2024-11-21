# Proxmox VE Setup Guide Using Rufus

This guide explains how to install Proxmox VE using a bootable USB drive created with Rufus.

---

## **Step 1: Download Proxmox VE ISO**
1. Visit the [Proxmox VE Download Page](https://www.proxmox.com/en/downloads).
2. Download the latest **Proxmox Virtual Environment ISO Installer**.

---

## **Step 2: Download and Install Rufus**
1. Go to the [Rufus website](https://rufus.ie/).
2. Download the latest version of Rufus and install it on your computer.

---

## **Step 3: Prepare the USB Thumb Drive**
1. Insert a USB drive (minimum 2GB capacity) into your computer.
2. Open Rufus.

---

## **Step 4: Create a Bootable USB Drive**
1. In Rufus:
   - Under **Device**, select your USB thumb drive.
   - Under **Boot Selection**, click **Select** and choose the downloaded Proxmox ISO file.
   - Configure the options:
     - **Partition Scheme:** MBR (for BIOS systems) or GPT (for UEFI systems).
     - **File System:** Leave as default (FAT32).
2. Click **Start** to begin formatting and writing the ISO to the USB drive.
3. Confirm any warnings about overwriting data on the USB drive.

---

## **Step 5: Boot from the USB Drive**
1. Insert the USB drive into the target machine.
2. Restart the machine and enter the BIOS/UEFI setup by pressing the appropriate key (e.g., **F2**, **F12**, **Esc**, or **Del** during boot).
3. Change the boot order to prioritize the USB drive.
4. Save changes and reboot. The system will boot from the Proxmox installer USB.

---

## **Step 6: Install Proxmox VE**
1. When the Proxmox installer screen appears, select **Install Proxmox VE**.
2. Follow the prompts:
   - Accept the license agreement.
   - Select the target drive for installation (ensure the correct storage device is connected).
   - Configure regional settings (time zone, keyboard layout, etc.).
   - Set up the root password and an email address for notifications.
   - Configure the network (assign an IP address, hostname, and network settings).
3. Complete the installation and remove the USB drive when prompted.

---

## **Step 7: Access the Proxmox Web Interface**
1. Reboot the system after installation.
2. On another device, open a web browser and navigate to the Proxmox web interface using the assigned IP address:

3. Log in using the root credentials set during installation.

---

## **Additional Resources**
- [Proxmox Documentation](https://pve.proxmox.com/wiki/Main_Page)
- [Rufus Documentation](https://rufus.ie/)

---
