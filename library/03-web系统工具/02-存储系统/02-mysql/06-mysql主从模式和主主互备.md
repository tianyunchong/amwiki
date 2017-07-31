#### 主从模式
1. 修改a机器的my.cnf配置
```shell
server-id = 1
#同步的日志记录文件
log-bin=/data/mysqlback
#需要数据同步的数据库
binlog-do-db=backup_db
```
2. b机器my.cnf配置
```shell
server-id = 2
#主机a的地址
master-host=192.168.1.101
# 主机a提供给b的用户，该用户包含backup_db的操作权限
master-user=ym
# 访问密码
master-password=ym
# 端口
master-port=3306
# 重试间隔时间60s
master-connect-retry=60
# 同步的数据库
replicate-do-db=backup_db
```
3. 更改a的mysql权限给b
```shell
mysql>GRANT FILE ON *.* TO ym@’192.168.1.102′ IDENTIFIEDBY ‘ym’;
```
4. 重启a,b机器
```shell
# b机器
mysql>slave start;
#查看同步配置情况
#a机器
mysql>show master status;
#b机器
mysql>show slave status;
```

####实现双向热备
1-5 双向配置
