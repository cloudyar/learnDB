# Windows install mysql 5.5
---
my.ini的配置文件：
```
[mysql]
#设置mysql客户端默认字符集
default-character-set=utf8

[mysqld]
#设置3306端口
port=3306
#设置mysql的安装目录
basedir=C:\wamp-all\mysql-5.5.60
# 设置mysql数据库的数据的存放目录
datadir=C:\wamp-all\sqldata
# 允许最大连接数
max_connections=20
# 服务端使用的字符集默认为8比特编码的latin1字符集
character-set-server=utf8
# 创建新表时将使用的默认存储引擎
default-storage-engine=INNODB
```

忘记密码重置：
1. 打开my.cnf配置文件，找到[mysqld],然后在该行下面添加以下参数：
	skip-grant-tables
2. 重启mysql服务：service mysql restart
3. 登陆mysql，此时不需要密码，直接回车 #mysql -u root -p
4. 更改密码
```
mysql> use mysql;
mysql>  update user set authentication_string=password("123456") where user='root';
mysql> flush privileges;  # 刷新权限
```
注意：密码字段名 5.7 版本的是 authentication_string，之前的为 password。

修改完后，记得注释掉 my.cnf 中的 skip-grant-tables 参数，重启 MySQL 服务，就可以用你设置的密码登录了。