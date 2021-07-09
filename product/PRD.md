# Webmin

Webmin 是一个Linux系统管理员可视化界面（后台支持多语言切换），提供大量偏底层的操作，适合运维人员使用。

## 架构

Webmin 采用模块化开发，除了官方提供的[模块](https://doxfer.webmin.com/Webmin/Webmin_Modules)之外，还有如下知名的第三方模块：

* Virtualmin：它是 Webmin 的一个插件，它通过一个界面简化了多个虚拟主机的管理，类似于cPanel或Plesk。使用 Virtualmin，您可以管理用户帐户、Apache 虚拟主机、DNS 条目、MySQL 数据库、邮箱等
* Usermin：是一个主要针对普通用户（非root权限用户）的Webmin简化版本。
* Usermin：是一个内置在Webmin上层的的一个UI用户界面，用来管理虚拟系统，例如Xen、KVM以及OpenVZ等实体。利用Cloudmin你可以在单个界面中使用不同的虚拟化技术来创建、丢弃、重置大小、启动、关闭以及限制多个实体。

#### 如何安装第三方模块？

待调研

#### Webmin 默认会安装 Apache, MySQL 吗？

不会

## 安装

* [Webmin](https://doxfer.webmin.com/Webmin/Installation)
* [Virtualmin](https://www.virtualmin.com/download)，同时会安装 Webmin

## 用户体验

#### 是否可以设置服务器密码为 Web 默认密码？

官方 [faq](https://webmin.com/faq.html) 中有方案

#### HTTPS访问是否是必须的？

不是必须的

#### Webmin 是否可以管理多用户？

可以

#### Webmin是否支持 FTP 多用户管理？

暂时找不到，无法上传文件夹
