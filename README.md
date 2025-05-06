### Steps with Commands:

1. **Create the script** (`/home/name/dummy.sh`):
    
    ```bash
    sudo nano /home/name/dummy.sh
    ```
    
    Paste the following:
    
    ```bash
    #!/bin/bash
    
    while true; do
      echo "Dummy service is running... [$(date)]" >> /var/log/dummy-service.log
      sleep 10
    done
    ```
    
2. **Make the script executable**:
    
    ```bash
    sudo chmod +x /home/name/dummy.sh
    ```
    
3. **Create the systemd service file** (`/etc/systemd/system/dummy.service`):
    
    ```bash
    sudo nano /etc/systemd/system/dummy.service
    ```
    
4. **Reload systemd**:
    
    ```bash
    sudo systemctl daemon-reload
    ```
    
5. **Enable and start the service**:
    
    ```bash
    sudo systemctl enable dummy
    sudo systemctl start dummy
    ```
    
6. **Check the service status**:
    
    ```bash
    sudo systemctl status dummy
    ```
    
7. **Monitor the service logs**:
    
    ```bash
    sudo journalctl -u dummy -f
    ```
    
8. **Stop and restart the service** (for testing):
    
    ```bash
    sudo systemctl stop dummy
    sudo systemctl restart dummy
    ```
    
9. Log Output:
    
    ```bash
    tail -f /var/log/dummy-service.log
    Dummy service is running...
    Dummy service is running...
    ```
