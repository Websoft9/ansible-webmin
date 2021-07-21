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

## Apache 配置

## 修改时区

## FTP 管理

## 用户管理
