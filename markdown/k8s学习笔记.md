# k8s学习笔记

## 发展史

### 资源管理器对比

     MESOS：Apache 分布式资源管理器。2019-5 Twitter推出，使用K8S
     Docker Swarm :2019-7 阿里云宣布剔除
     K8S：Google开发，基于内部原有的容器资源管理器borg，用GO语言重新编译

### K8S及其优势

     轻量级：消耗资源小
     开源
     弹性伸缩
     负载均衡：IPVS

- 适合人群:软件工程师，测试工程师，运维工程师，软件架构师，项目经理

### 组件架构

master服务：

- API server：所有服务访问统一入口
- controllerManager：负责副本期望数目
- Scheduler：负责接收任务，选择合适的节点进行任务分配
- ETCD：键值对数据库，存储K8S集群所有重要信息（持久化）

node:

- Kubelet：直接跟容器引擎交互实现容器的生命周期管理
- Kube-proxy：负责写入规则至 IPTABLES、IPVS实现服务映射访问的

### POD

#### POD概念

#### 网络通讯方式