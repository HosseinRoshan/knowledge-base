# ✅ Adding a New IP Range in MikroTik RouterOS and pfSense Firewall

## Prerequisites

- Ensure Bugdasht VPN is enabled if required to access your devices.
- Have administrative access to both MikroTik RouterOS (via Winbox) and pfSense firewall.

---

## Steps on MikroTik RouterOS (Winbox)

1. **Connect to RouterOS**
   - Open Winbox and connect to your MikroTik router.

2. **Add New Internal IP Range**
   - Go to `IP` > `Addresses`.
   - Click `+` to add a new IP address.
   - Enter the new IP range with subnet (e.g., `192.168.2.1/24`).
   - Select the interface this IP range will be assigned to (e.g., `ether2` or bridge interface).
   - Click `OK` to save.

---

## Steps on pfSense Firewall

1. **Access pfSense**
   - Log in to your pfSense firewall web interface.

2. **Add Static Route for New IP Range**
   - Navigate to `System` > `Routing` > `Static Routes` (or `System` > `Advanced` > `Firewall & NAT` > `Routes` depending on version).
   - Click `Add` to create a new static route.
   - Set the **Destination network** as your new IP range (e.g., `192.168.2.0/24`).
   - Set the **Gateway** to point to your MikroTik router’s IP on pfSense's network.
   - Save and apply changes.