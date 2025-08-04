# ✅ Split-DNS Setup Checklist (dnsmasq)

## 1. Install dnsmasq
```bash
sudo apt update
sudo apt install dnsmasq -y
```

---

## 2. Configure dnsmasq
Edit `/etc/dnsmasq.conf`:
```ini
# Listen only on localhost
listen-address=127.0.0.1
bind-interfaces

# Do not read /etc/resolv.conf
no-resolv
no-poll

# Security options
domain-needed
bogus-priv

# DNS servers for .ir domains (local/national resolvers)
server=/ir/10.202.10.202
server=/ir/10.202.10.102

# DNS servers for international domains
server=8.8.8.8
server=1.1.1.1

# Optional cache size
cache-size=1000
```

---

## 3. Enable and restart service
```bash
sudo systemctl enable dnsmasq
sudo systemctl restart dnsmasq
```

---

## 4. Configure system DNS
Update `/etc/resolv.conf`:
```text
nameserver 127.0.0.1
```

(Optional: lock the file to prevent overwrites)
```bash
sudo chattr +i /etc/resolv.conf
```

---

## 5. Test DNS resolution
```bash
dig mx postbank.ir @127.0.0.1   # should use IR resolvers
dig mx gmail.com @127.0.0.1     # should use international resolvers
```

---

## 6. (Optional) Logging
Enable logs in `/etc/dnsmasq.conf`:
```ini
log-queries
log-facility=/var/log/dnsmasq.log
```

Then:
```bash
sudo touch /var/log/dnsmasq.log
sudo chmod 644 /var/log/dnsmasq.log
sudo systemctl restart dnsmasq
tail -f /var/log/dnsmasq.log
```

---

✅ Now your mail server will correctly resolve `.ir` domains using national DNS servers and all other domains using international resolvers.