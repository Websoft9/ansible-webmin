---
sidebarDepth: 3
---

# Parameters

The Webmin deployment package contains a sequence of software (referred to as "components") required for Webmin to run. Below list the important information, the component name, installation directory path, configuration file path, port, version, etc.

## Path

This solution use Docker to deploy all service, you can run the command `docker ps` to list them  

### Webmin

Webmin installation directory:  */data/webmin*  
Webmin logs directory:  */data/logs/webmin*  

### Apache

Apache vhost configuration file: */etc/httpd/conf.d/vhost.conf*    
Apache main configuration file: */etc/httpd/conf/httpd.conf*   
Apache logs file: */var/log/httpd*  
Apache module configuration file: */etc/httpd/conf.modules.d/00-base.conf*   

### Docker

Docker root directory: */var/lib/docker*  
Docker image directory: */var/lib/docker/image*   
Docker daemon.json: please create it when you need and save to to the directory */etc/docker*   

## Ports

Open or close ports by **[Security Group Setting](https://support.websoft9.com/docs/faq/tech-instance.html)** of your Cloud Server to decide whether the port can be accessed from Internet.  

You can run the cmd `netstat -tunlp` to check all related ports.  

The following are the ports you may use:

| Name | Number | Use |  Necessity |
| --- | --- | --- | --- |
| TCP | 80 | HTTP to access Webmin by Apache | Required |
| TCP | 443 | HTTPS to access Webmin by Apache| Optional |
| TCP | 10000 | HTTP to access Webmin directly | Optional |

## Version

You can see the version on product pages at Marketplace. However, after being deployed to your server, the components will be updated automatically, resulting in a certain change in the version number. Therefore, run the command on the server to view the exact version number. 

```shell
# Check all components version
sudo cat /data/logs/install_version.txt

# Linux Version
lsb_release -a

# Docker Version
docker -v

# Apache Version
httpd -v

# Webmin version
cat /data/apps/webmin/
```
