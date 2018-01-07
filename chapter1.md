# 本地web服务器配置
>Mac 自带 apache2 服务器(macOS Sierra,Ver 10.12.6).



###1.修改 httpd.conf 目录.
###2.修改 httpd-vhosts.conf 
###3.控制的命令
```
sudo apachectl start

sudo apachectl stop
```

***
***
***


###1.修改 httpd.conf 目录.

> /private/etc/apache2/httpd.conf

```
#去除前面的#号,使得 apache2 支持 php
LoadModule php5_module libexec/apache2/libphp5.so

#修改Directory
<Directory />
    AllowOverride none
    Require all granted
</Directory>

#把目录改为自己的目录(Mac 限制了只能在 user 中的 Sites 下建立主目录)
DocumentRoot "/Users/tianzeng/Sites"
<Directory "/Users/tianzeng/Sites">
#发现也可以在 /private/etc/apache2/extra/httpd-userdir.conf 下修改主目录，但没验证

```

***

#2.修改 httpd-vhosts.conf 
>/private/etc/apache2/extra/httpd-vhosts.conf 

```
#可以用域名代替 localhost
<VirtualHost *:80>
    DocumentRoot "/Users/tianzeng/Sites"
    ServerName www.mysites.com
    ErrorLog "/private/var/log/apache2/sites-error_log"
    CustomLog "/private/var/log/apache2/sites-access_log" common
    <Directory />
                Options Indexes FollowSymLinks MultiViews
                AllowOverride None
                Order deny,allow
                Allow from all
      </Directory>
</VirtualHost>


```