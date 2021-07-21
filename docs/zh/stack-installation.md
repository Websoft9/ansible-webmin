# 初始化安装

在云服务器上部署 Webmin 预装包之后，请参考下面的步骤快速入门。

## 准备

1. 在云控制台获取您的 **服务器公网IP地址** 
2. 在云控制台安全组中，检查 **Inbound（入）规则** 下的 **TCP:80** 端口是否开启
3. 若想用域名访问 Webmin，请先到 **域名控制台** 完成一个域名解析

## Webmin 安装向导

1. 使用本地电脑的 Chrome 或 Firefox 浏览器访问网址：*http://服务器公网IP*, 进入登录页面
   ![Webmin 登录页面](https://libs.websoft9.com/Websoft9/DocsPicture/zh/webmin/webmin-login-websoft9.png)

2. 输入账号密码（[不知道账号密码？](/zh/stack-accounts.md#webmin)），成功登录到 Webmin 后台  
   ![Webmin 登录](https://libs.websoft9.com/Websoft9/DocsPicture/zh/webmin/webmin-dashboard-websoft9.png)

   > Webmin 默认以服务器的 root 用户作为账号

3. 设置语言：依次打开菜单【Webmin】>【Change Language and Theme】重设所需的语言
   ![Webmin 设置语言](https://libs.websoft9.com/Websoft9/DocsPicture/zh/webmin/webmin-changelangs-websoft9.png)

4. 系统管理：通过【系统】菜单可以进行系统管理，如修改密码及用户及群组、软件包管理等
   ![Webmin 系统管理](https://libs.websoft9.com/Websoft9/DocsPicture/zh/webmin/webmin-system-websoft9.png)

5. 服务器管理：通过【服务器】菜单可以进行服务器管理，如 Apache web服务、SSH服务等
   ![Webmin 服务器管理](https://libs.websoft9.com/Websoft9/DocsPicture/zh/webmin/webmin-server-websoft9.png)

5. 文件管理：通过【Tools】>【File Manage】菜单可以进行目录、文件管理，如新建文件夹、上传文件、修改文件的权限等
   ![Webmin 文件管理](https://libs.websoft9.com/Websoft9/DocsPicture/zh/webmin/webmin-file-websoft9.png)

6. 点击菜单下方的【>_】图标，进入 SSH 命令行模式（ESC 键取消）
   ![Webmin SSH 模式](https://libs.websoft9.com/Websoft9/DocsPicture/zh/webmin/webmin-sshcli-websoft9.png)

7. 完成其他所需的配置

> 需要了解更多 Webmin 的使用，请参考官方文档：[Webmin Documentation](http://doxfer.webmin.com/Webmin/Main_Page)

## Webmin 入门向导

现在开始针对于如何使用 Webmin 安装一个 WordPress 网站，做出一个完整的说明：  

### 准备环境

本部署方案中默认已经安装 Apache，还缺少 PHP 和 MySQL。  

PHP 和 MySQL 的安装是比较麻烦的，所幸，我们可以使用 Websoft9 提供的自动化脚本完成安装

1. 运行下面的命令，安装 PHP，其中版本选择 7.4
   ```
   git clone https://github.com/Websoft9/role_php.git
   ansible-playbook role_php/tests/test.yml
   ```

2. 运行下面的命令，安装 MySQL，其中版本选择 5.7
   ```
   git clone https://github.com/Websoft9/role_mysql.git
   ansible-playbook role_php/tests/test.yml
   ```

3. 登录到 Webmin 后台，点击左侧菜单下方的【刷新模块】按钮


### 上传源码

先下载 WordPress 到本地，然后上传、解压、修改文件权限。

1. 通过菜单打开【Tools】>【File Manager】 选择进入/data/wwwroot/default 目录，点击“File”下拉菜单，选择“Upload to current directory”完成wordpress压缩包上传：
   ![Webmin 上传](http://libs.websoft9.com/Websoft9/DocsPicture/zh/webmin/wb01.png)

1. 选中软件压缩包，鼠标右键中选择“Extract”,文件开始解压缩。
   ![Webmin 解压](http://libs.websoft9.com/Websoft9/DocsPicture/zh/webmin/wb02.png)

2. 文件解压后，多了1个目录：
   ![Webmin 解压](http://libs.websoft9.com/Websoft9/DocsPicture/zh/webmin/wb03.png)

3. 选中目录，鼠标右键“Properties”->“Change Ownership”，开始授权:
   ![Webmin 修改文件权限](http://libs.websoft9.com/Websoft9/DocsPicture/zh/webmin/wb04.png)

4. 设置用户www用户组www，勾选Recursive，最后点击“Change”。
   ![Webmin 修改文件权限](http://libs.websoft9.com/Websoft9/DocsPicture/zh/webmin/wb05.png)

### 创建数据库

1. 打开菜单【服务器】->“【ySQL数据库服务器】，点击“创建新的数据库”。
   ![Webmin MySQL数据库服务器](http://libs.websoft9.com/Websoft9/DocsPicture/zh/webmin/wb06.png)

2. 设置你的数据库名称
   ![](http://libs.websoft9.com/Websoft9/DocsPicture/zh/webmin/wb07.png)

### 配置虚拟主机

配置虚拟主机，需提前将域名解析到服务器。解析成功后，参考下面配置完成虚拟主机设置：

1. 打开菜单【服务器】->【Apache服务器】，点击“Create virtual host”。注意：请使用您自己的域名，且配置域名解析到该服务器IP。
   ![](http://libs.websoft9.com/Websoft9/DocsPicture/zh/webmin/wb08.png)

2. 点击右上角按钮，使域名设置生效：
   ![](http://libs.websoft9.com/Websoft9/DocsPicture/zh/webmin/wb09.png)

3. 本地浏览器访问：http://域名，测试 WordPress
   ![](http://libs.websoft9.com/Websoft9/DocsPicture/zh/webmin/wb10.png)

## 常见问题

#### 浏览器打开IP地址，无法访问 Webmin（白屏没有结果）？

您的服务器对应的安全组 80 端口没有开启（入规则），导致浏览器无法访问到服务器的任何内容

#### Webmin 默认使用的哪个端口？

默认使用 10000 端口，但本部署方案采用 Apache 进行了转发访问

