##### 安装docker和docker-compose
https://www.yuque.com/ordinarykai/notes/pp3xwo#oqUh8  

##### docker和docker-compose常见命令
https://www.yuque.com/ordinarykai/notes/pp3xwo#noDM5  

##### docker-compose一键部署基础服务组件
0. 创建docker-compose外部网络
```shell
docker network create app_net
```
1. 将docker-compose目录放到linux根目录  
2. redis data目录 和 redis.log文件 赋予读写权限
```shell
chmod +777 /docker-compose/env/reids/data
chmod +777 /docker-compose/env/reids/log/redis.log
```
3. 执行如下命令启动docker-compose-env中的基础组件服务
```shell
cd /docker/env
docker compose up -d --build
```
4. 查看docker-compose中所有服务
```shell
cd /docker/env
docker compose ps
```
5. 停止全部服务  
```shell
cd /docker/env
docker compose down
```
6. 停止特定服务  
```shell
docker stop [特定服务的容器名称]
```
7. 基础服务信息  
```text
mysql 8.0: 3306 root/root
nginx 7.0: 80
redis 1.23.0: 6379
```

##### docker-compose一键部署java服务
启动步骤同【docker-compose一键部署基础服务组件】  
本次一键部署java服务只是为了测试，在app目录下，只有hello.jar  
启动后访问http://ip:8080/hello (ip为linux的IP地址)，返回`hello,docker-compose!`即表示部署成功