# mysql用户设置
---
## 新增用户
1. 在mysql数据库中的user表添加新用户即可
```
//比如添加用户guest，密码为guest123，并授权用户进行select,insert,update权限
root@host# mysql -u root -p
Enter password:*******
mysql> use mysql;
Database changed
mysql> insert into user
		(host,user,password,
			select_priv,insert_priv,update_priv)
		values ('localhost','guest',password('guest123'),'Y','Y','Y');
Query OK, 1 row affected (0.20 sec)

//flush privileges;刷新权限表
mysql> FLUSH PRIVILEGES;
mysql> select host,user,password from user;
```
这个方法好像会报：ERROR 1364 (HY000): Field 'ssl_cipher' doesn't have a default value。
2. grant命令:给指定数据库TUTORIALS添加用户 zara ，密码为 zara123 
```
mysql> grant select,insert,update,delete,create,drop
		on tutorials.*
		to 'zara'@'localhost'
		identified by 'zara123';
```

## 常见管理mysql命令
1. use 数据库名;
2. show databases;
3. show tables;
4. show cloumns from 数据表;
5. show index from 数据表;
6. show table status like [from db_name][like 'pattern']\G:
该命令将输出Mysql数据库管理系统的性能及统计信息。
