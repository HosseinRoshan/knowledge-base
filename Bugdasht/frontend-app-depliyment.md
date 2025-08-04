# ✅ React Frontend App Deployment Checklist

- [ ] Turn on **Bugdasht VPN**  
- [ ] Connect to **BD-V3-Frontend server** via SSH  
- [ ] Gain root access using:  
  ```bash
  sudo su
  ```
- [ ] Go to the project directory:
  ```bash
  /var/www/bugdasht-front-v3
  ```
- [ ] Get the latest changes from Git:
  ```bash
  git pull
  ```
- [ ] Build the latest version of the project:
  ```bash
  npm run-script build
  ```
- [ ] Go to the parent directory where the old build exists:
  ```bash
  cd ..
  ```
- [ ] Back up the old build:
  ```bash
  mv build build.bk
  ```
- [ ] Copy the new build into the current directory:
  ```bash
  cp -r bugdasht-front-v3/build/ .
  ```
- [ ] Change the owner of the build directory:
  ```bash
  chown -R www-data:www-data build
  ```