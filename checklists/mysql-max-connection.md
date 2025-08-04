# ✅ Increasing MySQL Max Connections

## Steps

1. **Edit the MySQL Configuration File**

   Open the MySQL configuration file in your preferred text editor:
   ```bash
   vi /etc/my.cnf
   ```

2. **Locate or Add the `max_connections` Setting**

- Find the `[mysqld]` section.
- Add or modify the following line to increase the max allowed connections (e.g., to 500):
  ```
  max_connections = 500
  ```

3. **Save and Exit**

- Save the changes and exit the editor.

4. **Restart the MySQL Service**

- Apply the changes by restarting MySQL:
  ```
  systemctl restart mysqld
  ```
  *or on some systems:*
  ```
  service mysql restart
  ```

5. **Verify the New Setting**

- After MySQL restarts, verify the new value:
  ```
  SHOW VARIABLES LIKE 'max_connections';
  ```

---

## Notes

- **Be mindful:** Raising `max_connections` increases memory usage. Ensure your server has enough resources.
- **Backup** your configuration file before making changes.
- If running MySQL inside a container, adjust the relevant config or deployment method.