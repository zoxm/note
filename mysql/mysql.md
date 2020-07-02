#### mysql 8.0创建一个和root用户具有相同权限的用户

```sql
-- C:\Users\test>mysql -V
-- mysql  Ver 8.0.16 for Win64 on x86_64 (MySQL Community Server - GPL)

-- 注意：不同mysql版本命令也会有所不同
-- 在MySQL 8.04前，执行：SET PASSWORD=PASSWORD('[新密码]');但是MySQL8.0.4开始，这样默认是不行的。  	因为之前，MySQL的密码认证插件是“mysql_native_password”，而现在使用		 	是“caching_sha2_password”。
-- 创建一个和root用户具有相同权限的用户脚本
use mysql;
select user,host,authentication_string from user;
-- 如果存在用户先删除 注意：删除需要刷新，不然create时候会报错
mysql> delete from user where user='test';
Query OK, 1 row affected (0.01 sec)

mysql> flush privileges;
Query OK, 0 rows affected (0.00 sec)

-- 创建用户
mysql> create user 'test'@'%' identified with caching_sha2_password  by 'test';
Query OK, 0 rows affected (0.01 sec)

-- 表权限
mysql> grant all privileges on *.* to 'test'@'%' ;
Query OK, 0 rows affected (0.01 sec)

-- 授权 注意：这是mysql8版本以上的命令
mysql> alter user 'test'@'%' identified with mysql_native_password by 'test';
Query OK, 0 rows affected (0.01 sec)

-- 刷新 使生效
mysql> flush privileges;
Query OK, 0 rows affected (0.00 sec)


```

#### 常见问题解决方案


###### 1.没有权限。

在执行

```alter user 'test'@'%' identified with mysql_native_password by 'test';```

时候报错

```
ERROR 1227 (42000): Access denied; you need (at least one of) the SYSTEM_USER privilege(s) for this operation
```

查看权限，果然是空的

```
mysql> select * from mysql.user where user='test';
Empty set (0.00 sec)
```





