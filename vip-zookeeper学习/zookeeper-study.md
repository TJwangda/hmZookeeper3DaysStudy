## 基础介绍

> client 连接的节点不是leader时，连接到follower或者observer节点时，请求会转发给leader，不会自己处理。

1. server.3=localhost:2889:3889:observer  标识为observer节点

> 配置文件

1. zoo.cfg中的路径需要自己创建出来，否则无法启动集群
2. dataDir路径下创建myid文件，存数字id。

> 常用命令

~~~shell
# ---------单机-----------------------
# 启动 默认使用zoo.cfg配置文件
./zkServer.sh start

# ---------集群----------------------------
# 启动服务端
./zkServer.sh start /zookeeper某个配置文件路径/zoo.cfg
# 查看服务端启动状况
./zkServer.sh ststus /zookeep配置文件路径/zoo.cfg
# 关闭服务端
./zkServer.sh stop /zookeep配置文件路径/zoo.cfg
# 启动客户端
./zkCl.sh -server /zookeeper地址/端口号

# 创建节点，存在会报错
create /节点名  value
# 创建临时节点，ctrl+c退出临时节点再登录暂时不会删除，一会还是会删除（session存活倒计时）；quit退出会删除
create -e /节点名  value
~~~



## 详细功能

> 节点类型



> 三大框架