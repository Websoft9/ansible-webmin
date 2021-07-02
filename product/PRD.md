# Webmin

Webmin 是一个Linux系统管理员可视化界面（后台支持多语言切换），提供大量偏底层的操作，适合运维人员使用。

## 架构

Webmin 采用模块化开发，除了官方提供的[模块](https://doxfer.webmin.com/Webmin/Webmin_Modules)之外，还有如下知名的第三方模块：

* Virtualmin：它是 Webmin 的一个插件，它通过一个界面简化了多个虚拟主机的管理，类似于cPanel或Plesk。使用 Virtualmin，您可以管理用户帐户、Apache 虚拟主机、DNS 条目、MySQL 数据库、邮箱等
* Usermin：它是一个基于 web 的界面，用于 webmail、密码更改、邮件过滤器、fetchmail 等等。它是为 Unix 系统上的普通非 root 用户设计的，并将他们限制为通过 SSH 或控制台登录后能够执行的任务。有关Usermin 中内置的所有功能的列表，请参阅标准模块页面。

#### 如何安装第三方模块？

待调研

#### Webmin 默认会安装 Apache, MySQL 吗？

待调研

## 安装

* [Webmin](https://doxfer.webmin.com/Webmin/Installation)
* [Virtualmin](https://www.virtualmin.com/download)，同时会安装 Webmin

## 用户体验

#### 是否可以设置服务器密码为 Web 默认密码？

待调研

#### HTTPS访问是否是必须的？

待研究
