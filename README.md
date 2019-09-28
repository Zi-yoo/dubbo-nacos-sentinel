# Dubbo-Nacos-Sentinel
快速构建一个基础中台节点
## Nacos
服务治理中心
配置中心，实现配置文件热更新
### 生产化改造
配置中心的配置文件持久化--mysql
```
spring.datasource.platform=mysql
db.num=1
db.url.0=jdbc:mysql://127.0.0.1:3306/nacos_devtest?characterEncoding=utf8&connectTimeout=1000&socketTimeout=3000&autoReconnect=true
db.user=root
db.password=root
```
集群配置
修改cluster.conf,集群节点单数
```
ip:port
ip:port
ip:port
```
## Sentinel
生产化改造的Sentinel，DashBoard在仓库的Sentinel—Pro
### 客户端改造
查看dubbo-provider与dubbo-consumer模块
### 模块启动时添加上报信息
idea直接在VM options中添加
```
-Dcsp.sentinel.api.port=8720  //上报信息所用的端口
-Dcsp.sentinel.dashboard.server=127.0.0.1:8858 //Sentinel控制台地址与端口
-Dproject.name=dubbo-provider //在控制台显示的名字
```
