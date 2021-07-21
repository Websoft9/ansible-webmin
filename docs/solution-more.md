# More

Each of the following solutions has been proved to be effective and we hope it can give you help.

## Binding Domain

The precondition for binding a domain is that Webmin can accessed by domain name.

When there is only one website on the server, you can visit the website without binding domain. While considering the server security and subsequent maintenance, **Binding Domain** is necessary.

Steps for binding Webmin domain are as follows:

1. Connect your Cloud Server

2. Login to Webmin console, open:【Apache 服务器】>【编辑配置文件】
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/en/webmin/webmin-confapache001-websoft9.png)

3. Modify [Apache vhost file](/stack-components.md#apache) and set item **ServerName** to your value
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/en/webmin/webmin-confapache002-websoft9.png)

4. Save it and restart [Apache service](/admin-services.md#apache)

## Resetting Password

Webmin inherit the Linux user, so mean Webmin user and password is the same with Linux system.