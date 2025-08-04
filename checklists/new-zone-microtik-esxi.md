# ✅ Creating a New VLAN (Zone) in MikroTik RouterOS

## Prerequisites

- Ensure you have VPN access (e.g. Bugdasht VPN) if required for your network.
- Have Winbox or WebFig available for connecting to MikroTik RouterOS.

---

## Steps

1. **Connect to RouterOS**
   - Launch Winbox.
   - Enter the RouterOS IP, username, and password.
   - Click `Connect`.

2. **Navigate to VLAN Interfaces**
   - Go to `Interfaces` in the left menu.
   - Click the `VLAN` tab (or right-click > `Add` > `VLAN`).

3. **Create the VLAN Interface**
   - Click the `+` button to add a new VLAN.
   - Set the following:
     - **Name:** (e.g., `VLAN10`)
     - **Type:** VLAN
     - **VLAN ID:** (choose your VLAN ID, e.g., `10`)
     - **Interface:** Select the physical interface (e.g., `ether1`, `bridge`, or as needed)
     - Click `OK` or `Apply`.

4. **(Optional) Assign IP Address to VLAN Interface**
   - Go to `IP` > `Addresses`.
   - Click `+` to add a new IP address.
   - Enter the IP address and subnet for the VLAN (e.g., `192.168.10.1/24`).
   - Choose the new VLAN interface as the target.
   - Click `OK`.

5. **(Optional) Configure DHCP for the VLAN**
   - Go to `IP` > `DHCP Server`.
   - Click `Setup` and select your new VLAN interface.
   - Follow the DHCP wizard to configure address pool, gateway, and DNS.

6. **(Recommended) Test the Configuration**
   - Connect a device to the VLAN port and verify it receives an IP address (if DHCP is set) and can communicate as intended.