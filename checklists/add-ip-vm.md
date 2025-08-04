# ✅ Add Static IP and Enable SSH Access on Ubuntu VM in ESXi

## Prerequisites

- Make sure Bugdasht VPN is connected if required.
- Have access to the ESXi web interface IP for VM management.

---

## Steps

1. **Open ESXi Interface**
   - Open a web browser and go to your ESXi host’s IP.
   - Log in to the ESXi web UI.

2. **Open Console for Your VM**
   - Select your target VM.
   - Click `Console` or `Launch Console` to open the VM terminal.

3. **Configure Static IP with Netplan**
   - In the VM terminal, navigate to the netplan config directory:
     ```
     cd /etc/netplan/
     ```
   - Open the netplan YAML config file for editing (filename may vary, e.g., `01-netcfg.yaml`):
     ```
     sudo nano 01-netcfg.yaml
     ```
   - Modify or add the static IP, gateway, and DNS settings similar to this example, replacing with your own values and interface name:
     ```
     network:
       version: 2
       renderer: networkd
       ethernets:
         enp0s3:
           dhcp4: no
           addresses:
             - 192.168.10.100/24
           gateway4: 192.168.10.1
           nameservers:
             addresses: [8.8.8.8, 8.8.4.4]
     ```
   - Save and exit (`Ctrl+O`, `Enter`, `Ctrl+X` in nano).

4. **Apply Netplan Configuration**
   ```bash
   sudo netplan apply
   ```

5. **Enable and Start SSH Service**
- Check SSH service status:
  ```
  sudo systemctl status ssh
  ```
- Enable SSH to start on boot:
  ```
  sudo systemctl enable ssh
  ```
- Start SSH service if not running:
  ```
  sudo systemctl start ssh
  ```

6. **Verify SSH Access**
- From your local machine or management station, try to SSH into the VM using the static IP:
  ```
  ssh username@192.168.10.100
  ```
- Replace `username` and IP address with your VM’s login and assigned IP.