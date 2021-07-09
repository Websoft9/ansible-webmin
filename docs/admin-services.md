# Start or Stop the Services

These commands are required when you use the Webmin of Websoft9.

### Webmin

```shell
sudo systemctl start webmin-server
sudo systemctl stop webmin-server
sudo systemctl restart webmin-server
sudo systemctl status webmin-server

# you can use this debug mode if Webmin service can't run
webmin-server console
```

### MySQL

```shell
sudo systemctl start mysql
sudo systemctl stop mysql
sudo systemctl restart mysql
sudo systemctl status mysql
```

### MySQL on Docker

```shell
sudo docker start redmine-mysql
sudo docker restart redmine-mysql
sudo docker stop redmine-mysql
sudo docker stats redmine-mysql
```

### Redis

```shell
systemctl start redis
systemctl stop redis
systemctl restart redis
systemctl status redis
```

### phpMyAdmin

```shell
sudo docker start phpmyadmin
sudo docker stop phpmyadmin
sudo docker restart phpmyadmin
sudo docker stats pgadmin
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

### Nginx

```shell
sudo systemctl start nginx
sudo systemctl stop nginx
sudo systemctl restart nginx
sudo systemctl status nginx
```
