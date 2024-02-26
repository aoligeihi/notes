## 安装包下载

rabbitmq:[rabbitmq下载地址](https://www.rabbitmq.com/install-generic-unix.html)
Erlang: [Erlang下载地址](https://www.erlang.org/downloads)
socat(erlang的内存管理): [socat下载地址](http://www.dest-unreach.org/socat/download) 任意版本
Erlang和RabbitMQ版本对照：[版本对照地址](https://www.rabbitmq.com/which-erlang.html)

## 安装
#### 安装erlang
```shell
rpm -ivh erlang-23.3.4.11-1.el7.x86_64.rpm
```
#### 安装socat
```shell
rpm -ivh socat-1.7.3.2-2.el7.x86_64.rpm
```
#### 安装rabbitmq
```shell
rpm -ivh rabbitmq-server-3.8.16-1.el7.noarch.rpm
```
开机启动: `chkconfig rabbitmq-server on`
启动服务: `/sbin/service rabbitmq-server start`
查看服务状态: `/sbin/service rabbitmq-server status`
停止服务: `/sbin/service rabbitmq-server stop`
开启web管理插件(先将服务关闭掉): `rabbitmq-plugins enable rabbitmq_management`
访问地址: [http://ip:15672](http://ip:15672) (默认端口号: 15672), 如访问不了,查看是否开启防火墙

## 添加新用户

创建账号
```shell
rabbitmqctl add user [账户名] [密码]
```
设置用户角色
```shell
rabbitmqctl set_user_tags [账户名] administrator 
```
设置用户权限
```shell
rabbitmqctl set_permissions [-p <vhostpath>] <user> <conf> <read> #该命令为模板
rabbitmqctl set_permissions -p */* [账户名] *.**  *.**  *.** 
# 用户[XXX]具有/vhost1 这个virtual host中的所有的配置,写,读权限
```
查看当前用户和角色
```shell
rabbitmqctl list_users
```
