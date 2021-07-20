# FAQ

#### Webmin 是否支持多语言？

支持（包含中文），控制台自由切换

#### 本项目中 Webmin 采用何种安装方式？

采用 rpm/deb 包的安装方式

#### 新装的 Webmin 模块为何任然显示在 Un-used Modules 菜单下？

安装模块后，点击【刷新模块】才可将模块自动显示在正常的菜单下

#### HTTP Tunnel 有什么作用？

待研究

#### Webmin 中是否包含 Apache？

不包含

#### 是否可以通过命令行修改 Webmin 后台密码？

Webmin 使用的是服务器 root 密码，因此用 `passwd` 系统命令即可

#### 如果没有设置 HTTP 是否运行 Webmin？

可以，访问`http://服务器公网IP:10000` 即可

#### 是否可以修改Webmin的源码路径？

不可以

#### 如何修改上传的文件权限?

```shell
# 拥有者
chown -R apache.apache /data/wwwroot/
# 读写执行权限
find /data/wwwroot/ -type d -exec chmod 750 {} \;
find /data/wwwroot/ -type f -exec chmod 640 {} \;
```

#### 部署和安装有什么区别？

部署是将一序列软件按照不同顺序，先后安装并配置到服务器的过程，是一个复杂的系统工程。  
安装是将单一的软件拷贝到服务器之后，启动安装向导完成初始化配置的过程。  
安装相对于部署来说更简单一些。 

#### 云平台是什么意思？

云平台指提供云计算服务的平台厂家，例如：Azure,AWS,阿里云,华为云,腾讯云等

#### 实例，云服务器，虚拟机，ECS，EC2，CVM，VM有什么区别？

没有区别，只是不同厂家所采用的专业术语，实际上都是云服务器
