# 更多...

下面每一个方案，都经过实践证明行之有效，希望能够对你有帮助

## 域名绑定

绑定域名的前置条件是：已经完成域名解析（登录域名控制台，增加一个A记录指向服务器公网IP）  

完成域名解析后，从服务器安全和后续维护考量，需要完成**域名绑定**：

Webmin 域名绑定操作步骤：

1. 确保域名解析已经生效  

2. 登录 Webmin 控制台，打开：【Apache 服务器】>【编辑配置文件】
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/webmin/webmin-confapache001-websoft9.png)

3. 修改 [Apache虚拟机主机配置文件](/zh/stack-components.md#apache)，将其中的 **ServerName** 项的值修改为你的域名
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/webmin/webmin-confapache002-websoft9.png)

4. 保存配置文件，重启 [Apache 服务](/zh/admin-services.md#apache)

## 修改密码

Webmin 默认使用的是服务器 root 账号，修改服务器密码即修改 Webmin 密码。  

故，用 `passwd` 系统命令即可

## Apache 服务器配置

Webmin Apache 配置虚拟主机的操作如下：

要配置的域名为 test3.websoft9.cn，对应 WordPress 网站的根目录是/data/wwwroot/wordpress，接下来为该站点添加配置文件，设置域名、访问目录等（根据这个方法重复多次，就可以配置不同的网站的域名）:

1. 通过 http://IP地址，登录webmin面板工具。

2. 通过菜单中的“服务器”-》“Apache服务器”打开服务器配置。

3. 通过“Create virtual host”创建新的虚拟主机，填写参数，然后点击“创建”。
   > 配置说明
     服务端口：80
     网站目录: /data/wwwroot/wordpress 
     网站域名：xtrack.cn(测试用域名)
     配置文件：xtrack.conf，放在Apache配置文件目录下 /etc/httpd/conf.d/

   ![Webmin Apache](https://libs.websoft9.com/Websoft9/DocsPicture/zh/webmin/webmin-apache-vhost-websoft9.png)

4. 通过SSH模式查看生产配置文件

   ![Webmin Apache](https://libs.websoft9.com/Websoft9/DocsPicture/zh/webmin/webmin-apache-vhost-conf-websoft9.png)


## 修改时区

## FTP 管理

通过【Tools】 > 【File Manage】菜单可以进行文件管理，如文件的上传、下载等

选择 Wordpress 文件夹，点击【file】下拉菜单，选择“上传到当前目录”，完成文件上传

   ![Webmin File](https://libs.websoft9.com/Websoft9/DocsPicture/zh/webmin/webmin-ftp-websoft9.png)

## 用户管理

通过【系统】 > 【用户与群组】菜单可以进行用户及角色（分组）管理，如新增用户和编辑用户

选择“创建新用户”或点击用户列表中的用户可以实现用户添加和编辑操作。

   ![Webmin File](https://libs.websoft9.com/Websoft9/DocsPicture/zh/webmin/webmin-user-websoft9.png)
