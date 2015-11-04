---
layout: post
title: linux sysctl
category: [linux]
tag: [sysctl, linux]
date: 2015-11-02
---
---

Linux内核参数设置文件 sysctl.conf

文件路径：```/etc/sysctl.conf ```

查看所有可读变量： ```sysctl -a```

---

##case1：屏蔽远程ping主机

    vi /etc/sysctl.conf
    
    #在文件最后加入：
    
    # Disable ping requests
    net.ipv4.icmp_echo_ignore_all = 1
    
    #保存退出后，执行
    sysctl -p

<!-- more -->

---

