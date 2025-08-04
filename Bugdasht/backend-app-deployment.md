# ✅ Backend App Deployment Checklist

- [ ] Turn on **Bugdasht VPN**
- [ ] Connect to **BD-V3 server** via SSH
- [ ] Gain root access using:
  ```bash
  sudo su
  ```  
- [ ] Get the latest changes from Git:
  ```bash
  git pull
  ```  
- [ ] Change the owner of the updated files:
  ```bash
  chown -R www-data:www-data [changed files]
  ```  
