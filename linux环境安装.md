## 防火墙

[https://blog.csdn.net/qq_24232123/article/details/79781527 ](https://blog.csdn.net/qq_24232123/article/details/79781527 https://blog.51cto.com/andyxu/2137046 )[https://zhuanlan.zhihu.com/p/445891257](https://zhuanlan.zhihu.com/p/445891257) centos7

```PowerShell
# 关闭防火墙
service iptables stop
# 验证
service iptables status
# 关闭防火墙的自动运行
chkconfig iptables off
# 验证
chkconfig --list | grep iptables
# 重启防火墙
service iptables restart
```

```PowerShell
# 查看防火墙状态
systemctl status firewalld.service
# 开启防火墙
systemctl start firewalld.service
# 关闭防火墙
systemctl stop firewalld.service
# 禁用防火墙服务
systemctl disable firewalld.service

# 查看防火墙规则
firewall-cmd –list-all
# 查询端口是否开放
firewall-cmd –query-port=8080/tcp
# 重启防火墙
firewall-cmd –reload
# 查看防火墙状态
firewall-cmd  --state
```

> hfghd