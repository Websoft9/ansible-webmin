# SSL/HTTPS

必须完成[域名绑定](/zh/solution-more.md)且可通过 HTTP 访问 Webmin ，才可以设置 HTTPS。

Webmin 预装包，已安装Web服务器 SSL 模块和公共免费证书方案 [Let's Encrypt](https://letsencrypt.org/) ，并完成预配置。因此，除了虚拟主机配置文件之外，HTTPS 设置则不需要修改 Nginx 其他文件。

## 快速指南

### 自动部署

如果没有申请证书，只需在服务器中运行一条命令`sudo certbot`便可以启动免费证书**自动**申请和部署

```
sudo certbot
```

### 手动部署

如果你已经申请了证书，只需三个步骤，即可完成 HTTPS 配置

1. 将申请的证书、 证书链文件和秘钥文件上传到 */data/cert* 目录
2. 打开虚拟主机配置文件：*/etc/httpd/conf.d/vhost.conf* ，新增**HTTPS 配置段** 到文件中
 ``` text
   <VirtualHost *:443>
    ServerName  webmin.yourdomain.com
    DocumentRoot "/data/apps/webmin"
    #ErrorLog "logs/webmin.yourdomain.com-error_log"
    #CustomLog "logs/webmin.yourdomain.com-access_log" common
    <Directory "/data/apps/webmin">
    Options Indexes FollowSymlinks
    AllowOverride All
    Require all granted
    </Directory>
    SSLEngine on
    SSLCertificateFile  /data/cert/webmin.yourdomain.com.crt
    SSLCertificateKeyFile  /data/cert/webmin.yourdomain.com.key
    SSLCertificateKeyFile  /data/cert/webmin.yourdomain.com.key
    </VirtualHost>
   ```
3. 修改域名信息，保存配置文件

4. 重启[ Apache 服务](/zh/admin-services.md#nginx)后生效
   ```
   sudo systemctl restart apache
   ```

## 专题指南

若参考上面的**快速指南**仍无法成功设置HTTPS访问，请阅读由Websoft9提供的 [《HTTPS 专题指南》](https://support.websoft9.com/docs/faq/zh/tech-https.html#nginx)

《HTTPS 专题专题》方案包括：HTTPS前置条件、HTTPS 配置段模板及故障诊断等具体方案。
