```
1、拉取镜像
docker pull container-registry.oracle.com/database/express:21.3.0-xe
2、tag镜像
docker tag container-registry.oracle.com/database/express:21.3.0-xe oracle21c
3、运行容器
docker run -it -d --name oracle21c -p 1525:1521 -p 5500:5500 -e ORACLE_PWD=123456 -e ORACLE_CHARACTERSET=UTF8 container-registry.oracle.com/database/express:21.3.0-xe
4、进入容器
docker exec -it oracle21c bash
5、连接数据库
sqlplus / as sysdba
# 修改system密码
alter user system identified by 123456;
6、退出sqlplus
exit
7、退出容器
exit
# 配置完成
```