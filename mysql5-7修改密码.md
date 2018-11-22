## 修改root初始密码
[修改初始密码](https://www.centos.bz/2017/08/centos-7-reset-mysql-5-7-root-password/)
## 已知密码修改密码
[修改密码](https://blog.csdn.net/qq_33472557/article/details/77726094)

## ubuntu18.04安装mysql5.7 2018年11月22日，亲测可用  
[安装及创建新用户](https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-18-04)  
创建用户并赋予访问权限：mysql> GRANT ALL PRIVILEGES ON *.* TO 'shi'@'localhost' WITH GRANT OPTION;  

## 查看mysql5.7中的数据库、数据表的编码格式，忽略格式修改，尽量在配置文件中修改（命令行修改是否会有重启失效的问题？） 2018年11月22日

[查看和修改 mysql库、表、字段编码](https://blog.csdn.net/springsunss/article/details/70337915)

## 用户访问数据库的权限

以shi账户为例添加数据库hello的访问权限

mysql> update mysql.user set authentication_string=password('访问数据库的密码') where user = 'shi'; //修改密码  

mysql> update mysql.user set host=localhost where user = 'shi';  //localhost 改为 '%'可远程连接  

mysql> grant all privilages on hello.* to 'shi'@'localhost';  

mysql> flush privileges;  

## [设置MySQL远程访问的权限 mysql5.7.24 ubuntu18.04](https://blog.csdn.net/princewwj/article/details/80525544)  

hello数据库为例，或者直接设置为 * 表示所有数据库  

1. 编辑mysql的启动配置文件  

sudo vim /etc/mysql/mysql.conf.d/mysqld.cnf  

加前缀#注释掉bind-address = 127.0.0.1  

2. 授权远程任意IP地址可以访问数据库  

mysql> grant all privilages on hello.* to 'shi'@"%" identified by "访问数据库的密码" with grant option;  

mysql> flush privileges;  

sudo ufw enable  

sudo ufw default deny  

sudo ufw allow 3306     


3. 重启mysql

sudo /etc/init.d/mysql restart

systemctl restart mysql.service

