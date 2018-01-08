#MAMP搭建
>详细教程: http://www.jianshu.com/p/d560ce2318c5
>http://www.jianshu.com/p/a665a6372e42
>Macintosh、Apache、MySQL和PHP



###1.下载 MAMP
>百度云下载破解版(1.先打开 mamp,再运行 mamp pro )
###[2.关闭原先系统的开发环境](#close_pre_envi)
###[3.成功运行](#successful)
###4.配置文件

###5.修改 mamp 的 mysql 的默认端口为 3307.

***
***
***

###2.关闭原先系统的开发环境<a name="close_pre_envi"/>
* 1.Mysql
```
sudo launchctl unload -F /Library/LaunchDaemons/com.oracle.oss.mysql.mysqld.plist
```
* 2.Apache2
```
sudo apachectl stop
```

***

###3.成功运行<a name="successful"/>
>http://localhost/MAMP/?language=English

***
###4.MAMP 各种文件路径
1.配置文件:
```/Library/Application Support/appsolute/MAMP PRO/conf```





