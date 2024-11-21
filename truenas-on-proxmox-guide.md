# TrueNAS on Proxmox VE

This guide explains how to install and configure TrueNAS as a virtual machine on Proxmox VE.

---

## **Step 1: Download TrueNAS ISO**
1. Visit the [TrueNAS Download Page](https://www.truenas.com/download/).
2. Download the latest TrueNAS CORE or SCALE ISO.

---

## **Step 2: Upload ISO to Proxmox**
1. In the Proxmox web interface, go to **Datacenter > Storage > ISO Images**.
2. Click **Upload** and select the downloaded TrueNAS ISO.

---

## **Step 3: Create the TrueNAS VM**
1. Click **Create VM** and configure:
   - **General**: Set a name (e.g., `TrueNAS`).
   - **OS**: Select the uploaded ISO and set Type to `Other`.
   - **System**: Use `OVMF (UEFI)` and `q35`.
   - **Disks**: Add a 16GB virtual disk for TrueNAS OS.
   - **CPU**: Allocate at least 2 cores.
   - **Memory**: Assign at least 8GB RAM.
   - **Network**: Use the **VirtIO** network adapter.

---

## **Step 4: Install TrueNAS**
1. Start the VM and open the console.
2. Follow the TrueNAS installer prompts:
   - Select the installation disk.
   - Set up a root password.
3. Reboot the VM after installation.

---

## **Step 5: Configure TrueNAS**
1. Access TrueNAS via a browser at `http://<truenas-ip>`.
2. Log in with the root credentials.
3. Set up:
   - Storage pools using additional disks.
   - Network shares (e.g., SMB, NFS).
   - Users and permissions.

---

## **Step 6: Optimize Proxmox for TrueNAS**
1. **Enable IO Threading**:
   ```bash
   qm set <vmid> --io-thread true
