# SSL/HTTPS

Before setting, you have to complete [binding domain](/solution-more.md) and make sure you can access Webmin by HTTP.

Webmin deployment package has installed the SSL module of Nginx and open Certificate Authority **[Let's Encrypt](https://letsencrypt.org/)** for you to configure the HTTPS quickly and conveniently.

> Except for the [vhost configuration file](/stack-components.md#nginx), it doesn't need modify any Nginx configuration file for HTTPS.

## Quick start

### Automatic deployment

If you want to use a free certificate, just run the one command `sudo certbot` on your instance to start the HTTPS deployment.

```
sudo certbot
```

### Manual deployment

If you have applied for a commercial certificate, complete the HTTPS configuration in just three steps:

1. Upload your certificate, file of the certificate chain and secret key to the directory: */data/cert*.

2. Open the vhost configuration file: */etc/httpd/conf.d/vhost.conf*.

3. Insert the **HTTPS template** into *vhost.conf* and modify your certificate path, ServerName.
   ``` shell
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
4. Save file and [restart Apache service](/admin-services.md).

## Special Guide

If failed to set HTTPS by taking the above steps, please view the [HTTPS Special Guide](https://support.websoft9.com/docs/faq/tech-https.html#nginx) provided by Websoft9, which includes solutions about configuring HTTPS pre-conditions, HTTPS configuration segment templates, precautions, detailed steps, troubleshooting and more.
