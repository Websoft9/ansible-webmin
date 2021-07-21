# FAQ

#### Does Webmin support multiple languages?

Yes, you can change language from Webmin console

#### What kind of installation method does Webmin use in this project?

Use rpm/deb

#### Why is the newly installed Webmin module still displayed under the Un-used Modules menu?

You should click【Refresh module】after the installation of new module

#### What is the function of HTTP Tunnel?

To be studied

#### How to disable Webmin inherit the Linux system user?

You can 【Unix验证】 更改为 【设置为】，同时设置新密码和用户

![](https://libs.websoft9.com/Websoft9/DocsPicture/en/webmin/webmin-usermode-websoft9.png)

#### Is Apache included in Webmin?

Does not contain. But in this deployment plan, we have additionally installed Apache

#### Can I reset password of Webmin by command? 

Webmin uses the server root password, so use the `passwd` system command

#### If there is no domain name, can I deploy Webmin?

Yes, access Webmin by *http://Server's Internet IP:10000*.

#### Is it possible to modify the source path of Webmin?

No

#### How to change the permissions of filesystem?

Change owner(group) or permissions as below:

```shell
chown -R apache.apache /data/wwwroot
find /data/wwwroot -type d -exec chmod 750 {} \;
find /data/wwwroot -type f -exec chmod 640 {} \;
```

#### What's the difference between Deployment and Installation?

- Deployment is a process of installing and configuring a series of software to the server in a different order, which is a complex system engineering.  
- Installation is the process of starting the initial wizard after the application is prepared.  
- Installation is simpler than deployment. 

#### What's Cloud Platform?

Cloud platform refers to platform manufacturers that provide cloud computing services, such as: **Azure, AWS, Alibaba Cloud, HUAWEI CLOUD, Tencent Cloud**, etc.

#### What is the difference between Instance, Cloud Server, Virtual Machine, ECS, EC2, CVM, and VM?

No difference. All refer to cloud servers. They are the different terminology used by manufacturers.
