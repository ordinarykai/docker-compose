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
2. 执行如下命令启动docker-compose中所有服务  
```shell
cd /docker
docker-compose up -d --build
```
3. 查看docker-compose中所有服务
```shell
docker-compose ps
```
4. 停止全部服务  
```shell
cd /docker
docker-compose down
```
5. 停止特定服务  
```shell
docker stop [特定服务的容器名称]
```
6. 服务端口  
```text
mysql: 3306
nginx: 80
redis: 6379
```