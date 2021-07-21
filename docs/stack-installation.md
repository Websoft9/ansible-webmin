# Initial Installation

If you have completed the Webmin deployment, follow the steps below to start a quick use.

## Preparation

1. Get the **Server's Internet IP** of Server on your Cloud Platform.
2. Check your **[Inbound of Security Group Rule](https://support.websoft9.com/docs/faq/tech-instance.html)** of Cloud Console to ensure the **TCP:80** is allowed.
3. Make a domain resolution on your Cloud Console if you want to use domain for Webmin.

## Webmin Installation Wizard

1. Use local browser to access the URL *http://DNS* or *http://Server's Internet IP*. You will enter login page
   ![Webmin Login](https://libs.websoft9.com/Websoft9/DocsPicture/en/webmin/webmin-login-websoft9.png)

2. Log in Webmin web console ([Don't have password?](/stack-accounts.md#webmin)) 
   ![Webmin Login](https://libs.websoft9.com/Websoft9/DocsPicture/en/webmin/webmin-dashboard-websoft9.png)

3. Open menu:【Webmin】>【Change Language and Theme】to set your language
   ![Webmin set language](https://libs.websoft9.com/Websoft9/DocsPicture/zh/webmin/webmin-changelangs-websoft9.png)

4. Click the 【>_】icon of left menu, go to SSH mode (ESC cancel)
   ![Webmin SSH Mode](https://libs.websoft9.com/Websoft9/DocsPicture/zh/webmin/webmin-sshcli-websoft9.png)

> More guide about Webmin, please refer to [Webmin Documentation](http://doxfer.webmin.com/Webmin/Main_Page).

## Webmin Setup wizard

Coming soon...

## Q&A

#### Can't visit the start page of Webmin?

Your TCP:80 of Security Group Rules is not allowed, so there is no response from Chrome or Firefox.

#### Which port Webmin used?

Use port:10000 by default, but this deployment solution use Apache for proxy
