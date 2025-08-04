# ✅ Sonar IP Whitelist Setup Checklist (pfSense)

- [ ] Go to **pfSense**
- [ ] Navigate to **Firewall > Rules > WAN**
- [ ] Add a **new rule** (at the end of the list)
- [ ] In **Source**:
  - [ ] Select **Single host or alias**
  - [ ] Enter the **IP/Alias** to whitelist
- [ ] In **Destination**:
  - [ ] Select **Single host or alias**
  - [ ] Enter the **Sonar internal IP**
- [ ] Set **Destination Port Range** to `8080` (or required port)
- [ ] Save the rule and apply changes on the main page

---

- [ ] Navigate to **Firewall > NAT > Port Forward**
- [ ] Add a **new NAT rule**
- [ ] In **Edit Redirect Entry** → **Source**:
  - [ ] Click **Display Advanced**
  - [ ] Select **Single host or alias**
  - [ ] Enter the **IP/Alias** to whitelist
- [ ] In **Destination Port Range**, set to `8080`
- [ ] In **Redirect target IP**, enter the **Sonar internal IP**
- [ ] In **Redirect target port**, set to `8080`
- [ ] Fill in the **Description**
- [ ] In **Filter rule association**, select your created rule
- [ ] Save the rule and apply changes on the main page

---

✅ After setup, you can access **Sonar** with the whitelisted IP from VPN:
```
46.245.92.205:800 (port 8080)
```