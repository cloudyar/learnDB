MySQL有几个关于character_set的变量：

1. character_set_client
2. character_set_connection
3. character_set_database
4. character_set_filesystem
5. character_set_results
6. character_set_server
7. character_set_system
8. character_set_dir

### 结论
1. character_set_client,character_set_connection,character_set_results这三个参数值是由客户端每次连接进来设置的，和服务器没有关系。（我们登陆进mysql后，执行```set names utf8;```实际就是同时修改上面的这3个参数值的。
> 通过CMD和Navicat分别连接MySQL得到的这三个参数不一样，跟服务器没有关系。
> 从实际上可以看到，当客户端连接服务器的时候，它会将自己想要的字符集名称发给mysql服务器，然后服务器就会使用这个字符集去设置character_set_client、character_set_connection、character_set_results这三个值。如cmd是用gbk，而SQLyog是用utf8。

### 其他几个参数
1. character_set_database： 当前所在的数据库字符集。
> 如果没有切换到其他数据库，则character_set_server和character_set_database是一样的。
2. character_set_filesystem
> 把os上文件名转化成此字符集，即把 character_set_client转换character_set_filesystem，默认binary是不做任何转换的
3. character_set_system
> character_set_system是个只读数据不能更改。也没多少改的意义，他是元数据的编码，相信不会有人用中文做数据库名和字段名之类的吧，这个字段和具体存储的数据无关。
4. character_sets_dir