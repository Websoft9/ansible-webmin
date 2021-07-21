# Start or Stop the Services

These commands are required when you use the Webmin of Websoft9.

### Webmin

```shell
sudo systemctl start webmin-server
sudo systemctl stop webmin-server
sudo systemctl restart webmin-server
sudo systemctl status webmin-server
```

### Apache

```shell
sudo systemctl start apache
sudo systemctl stop apache
sudo systemctl restart apache
sudo systemctl status apache
```

### Docker

```shell
sudo systemctl start docker
sudo systemctl restart docker
sudo systemctl stop docker
sudo systemctl status docker
```

### Docker-Compose
```
# Create Containers
sudo docker-compose up -d

# Remove Containers
sudo docker-compose up -d

# Start/Stop/Restart Containers
sudo docker-compose start
sudo docker-compose stop
sudo docker-compose restart
```