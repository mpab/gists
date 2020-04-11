#macOS
virtual hosts file
/etc/apache2/extra/httpd-vhosts.conf

##enable everything under ~/Sites

```xml
<VirtualHost *:80>
    DocumentRoot /Users/mick/Sites/test/web
    DirectoryIndex index.php
    <Directory "/Users/mick/Sites">
        Options Indexes FollowSymLinks
        Order Allow,Deny
        Allow from all
        AllowOverride all
        <IfModule mod_php5.c>
            php_admin_flag engine on
            php_admin_flag safe_mode off
            php_admin_value open_basedir none
        </ifModule>
    </Directory>
</VirtualHost>
```

restart apache

```console
$ sudo apachectl restart
```

##ssl
watch out for path capitalisation
https://discussions.apple.com/thread/8501107
https://websitebeaver.com/set-up-localhost-on-macos-high-sierra-apache-mysql-and-php-7-with-sslhttps

https://community.home-assistant.io/t/osx-server-with-apache-reverse-proxy-problem/37843/4

https://www.caribmendez.net/2016/12/apache-reverse-ssl-proxy/


