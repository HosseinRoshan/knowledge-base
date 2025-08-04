# ✅ Whitelist an IP Address in pfSense

- [ ] Turn on **Bugdasht VPN**  
- [ ] Go to the firewall address:
  ```bash
  http://172.17.9.1:65123
  ```
- [ ] Log in and navigate to:
  ```bash
  Firewall > NAT
  ```
- [ ] Add a **NAT rule** (move it to the top of the list)
- [ ] In **Source** row, enter the **IP/Range** you want to whitelist
- [ ] In **Destination**, select **WAN Address**
- [ ] In **Destination Port Range**, enter the **port your service runs on**
- [ ] In **Redirect target IP**, enter your **internal machine IP**
- Example: `172.10.10.1`
- [ ] In **Redirect target port**, enter your **service port** again
- [ ] Save and apply changes

---

✅ Test:  
From the **whitelisted external IP**, call the Firewall public IP with the service port:
  ```bash
  46.245.92.205:<your-service-port>
  ```