#  apache nifi调度工具绑定mongo后端服务
##  构建并运行apache nifi
```
oc new-app https://github.com/asiainfoLDP/apache-nifi-ocrhestration.git --context-dir=docker-nifi
oc expose svc apache-nifi-ocrhestration
```

##  创建mongo后端服务
```
oc new-backingserviceinstance my-mongodb \
--backingservice_name=MongoDB \
--planid=257C6C2B-A376-4551-90E8-82D4E619C852

oc bind my-mongodb apache-nifi-ocrhestration
```

## 查看mongo服务连接信息
```
oc describe bsi my-mongodb
```

##  浏览器登陆nifi并创建GetMongo节点
