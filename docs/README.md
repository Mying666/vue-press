---
sidebarDepth: 3
---
# Nginx
## nginx 介绍
### 什么是nginx
Nginx是一款高性能的http 服务器/反向代理服务器及电子邮件（IMAP/POP3）代理服务器。由俄罗斯的程序设计师Igor Sysoev所开发，官方测试nginx能够支支撑5万并发链接，并且cpu、内存等资源消耗却非常低，运行非常稳定。

### 应用场景
1、http服务器。Nginx是一个http服务可以独立提供http服务。可以做网页静态服务器。

2、虚拟主机。可以实现在一台服务器虚拟出多个网站。例如个人网站使用的虚拟主机。

3、反向代理，负载均衡。当网站的访问量达到一定程度后，单台服务器不能满足用户的请求时，

需要用多台服务器集群可以使用nginx做反向代理。并且多台服务器可以平均分担负载，

不会因为某台服务器负载高宕机而某台服务器闲置的情况。


## nginx安装
### 下载
Nginx官网提供了三个类型的版本：[官方地址](http://nginx.org/en/download.html)

Mainline version：Mainline 是 Nginx 目前主力在做的版本，可以说是开发版

Stable version：最新稳定版，生产环境上建议使用的版本

Legacy versions：遗留的老版本的稳定版

## 启动nginx
进入sbin目录，执行命令./nginx

[root@admin sbin]# ./nginx

## 查看nginx是否启动
[root@admin sbin]# ps -aux | grep nginx

## 关闭nginx
[root@admin sbin]# ./nginx -s stop

或者

[root@admin sbin]# ./nginx -s quit

## 重启nginx
先关闭，然后启动

## 刷新配置文件
[root@admin sbin]# ./nginx -s reload

## 关闭防火墙，开启远程访问
首先需要关闭防火墙：默认端口是80
### 方法一：永久开放80端口
/sbin/iptables -I INPUT -p tcp --dport 80 -j ACCEPT /etc/rc.d/init.d/iptables save
### 方法二：临时关闭系统防火墙
service iptables stop
### 方法三：永久关闭修改配置开机不启动防火墙
chkconfig iptables off

## 访问nginx

