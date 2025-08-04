# ✅ Creating a New VLAN (Port Group) in VMware ESXi

## Prerequisites

- Ensure VPN access (e.g., Bugdasht VPN) is enabled if needed to reach the ESXi management interface.
- Keep your VLAN ID from MikroTik (Winbox) setup handy.

---

## Steps

1. **Connect to ESXi Host Interface**
   - Open your web browser and enter the ESXi host’s IP address.
   - Log in with your administrative credentials.

2. **Navigate to Networking**
   - In the left sidebar, click on `Networking`.

3. **Create a New Port Group**
   - Go to the `Port Groups` tab.
   - Click `Add port group` (or `Add Networking` > `Virtual Machine Port Group for a Standard Switch`).
   - Set the following:
     - **Name:** Choose a descriptive name for your VLAN/zone (e.g., `VLAN10`).
     - **VLAN ID:** Enter the exact VLAN ID you created before on your MikroTik router.
     - **VSwitch:** Select the existing virtual switch.
       - If you do not have a virtual switch, go to the `Virtual Switches` tab and create one first.

4. **Finalize Port Group**
   - Click `Add` or `Finish` to create the new Port Group.

5. **Assign the VLAN Port Group to a Virtual Machine**
   - Go to the `Virtual Machines` section.
   - Select the VM you wish to assign to the new VLAN.
   - Click `Edit` to modify its hardware settings.
   - In the `Network Adapter` section, select your new VLAN port group from the dropdown list.
   - Save and apply the changes.