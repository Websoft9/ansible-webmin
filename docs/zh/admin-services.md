# 服务启停

使用由Websoft9提供的 Webmin 部署方案，可能需要用到的服务如下：

### Webmin

```shell
sudo systemctl start webmin
sudo systemctl stop webmin
sudo systemctl restart webmin
sudo systemctl status webmin
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
#创建容器编排
sudo docker-compose up -d

#删除容器编排
sudo docker-compose up -d

#启动/停止/重启
sudo docker-compose start
sudo docker-compose stop
sudo docker-compose restart
```
