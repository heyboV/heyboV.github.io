title: Ubuntu 16.0.4配置服务端Shadowsocks
id: 1510117194307
author: heybo
tags:
  - blog
  - ss
  - shadowsocks
  - ubuntu
categories: []
date: 2017-11-08 12:59:00
---
###### 更新软件及软件列表
    sudo apt-get update && sudo apt-get -y upgrade
###### 安装python-pip
    sudo apt-get install python-pip
###### 安装shadowsocks
    sudo pip install shadowsocks
###### 编辑配置文件
    sudo vi /etc/shadowsocks.json
    
    {
     "server":"your server IP",
     "server_port":a unused port number,
     "local_port":1080,
     "password":"you password",
     "timeout":600,
     "method":"aes-256-cfb"
     }
###### 启动
    sudo ssserver -c /etc/shadowsocks.json -d start
###### 配置shadowsocks自启动
    sudo vi /etc/rc.local
    ## add
    sudo ssserver -c /etc/shadowsocks.json -d start
That is all.