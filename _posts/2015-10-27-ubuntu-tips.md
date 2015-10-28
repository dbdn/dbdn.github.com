---
layout: post
title: ubuntu 使用笔记
category: ubuntu
date: 2015-10-27
duoshuo: true

---

---

##将/home目录下的中文改为英文
```
    #打开终端，在终端中输入命令:
    
    export LANG=en_US
    xdg-user-dirs-gtk-update
    
    #跳出对话框询问是否将目录转化为英文路径,同意并关闭.
    #在终端中输入命令:
    
    export LANG=zh_CN
    
    #关闭终端,并重起.下次进入系统,系统会提示是否把转化好的目录改回中文.选择不再提示,并取消修改.主目录的中文转英文就完成了~
```
--------
##网络设置
- 配置ip
ubuntu的网络配置信息放在（/etc/network/interfaces）

如果配置动态获取ip，则在上述文件中加入以下内容：

     auto eth0
     iface eth0 inet dhcp

如果配置静态ip，则添加如下内容：

     auto eth0
     iface eth0 inet static
     address 192.168.33.201
     netmask 255.255.255.0
     gateway 192.168.33.1
 
要是配置生效，需要重启网卡：

     ifconfig eth0 down
     ifconfig eth0 up

若还有没有配置成功，则需重启下网络服务

    /etc/init.d/networking restart
    
二、配置dns服务器 （/etc/resolv.conf）
```
## ubuntu 的dns服务器信息，放在 /etc/resolv.conf中
nameserver  114.114.114.114
```

----------