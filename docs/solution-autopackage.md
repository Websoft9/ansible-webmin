# Package Automation

Websoft9 provides a large number of Ansible-based [automated installation packages](https://github.com/search?q=org%3AWebsoft9+role_) for Webmin. You can easily install MySQL, Nginx, PostgreSQL, Java, PHP, Node, Python, Ruby and other basic environments.

Below is an example of MySQL for your reference:  

1. Get MySQL's github URL from [Websoft9](https://github.com/websoft9). e.g *https://github.com/Websoft9/role_mysql*

2. Git clone and install it
   ```
   git clone https://github.com/Websoft9/role_mysql.git
   ansible-playbook role_php/tests/test.yml
   ```

You can install other components use the same method.