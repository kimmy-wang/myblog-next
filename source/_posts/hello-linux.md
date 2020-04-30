---
title: centOS7在VirtualBox中装好后的网络连接问题
date: 2018-05-19 9:23:35
categories:
- 操作系统
tags:
- Linux
---

## 解决办法

### 设置网络连接方式

在VirtualBox中设置网卡连接方式：点“设置”，在弹出的界面中点“网络”，最后选择“连接方式”为“桥接网卡”

![Alt text](/images/hello-linux/setting.png)


<!--more-->


### 查看网络配置文件的名字

``` bash
$ vi ifconfig -a
```

如果显示ifconfig：command not found，忽略此步

### 编辑网络配置文件

用Vi编辑器打开配置文件，输入命令以下

``` bash
$ vi /etc/sysconfig/network-scripts/ifcfg-enp0s3
```

就会看到下图红框部分。

![Alt text](/images/hello-linux/setting1.png)

按"Insert"键进入编辑模式，把ONBOOT=no改为ONBOOT=yes，然后按"Esc"键退出编辑模式，最后输入“:wq”按回车键保存并退出

### 重启网络服务。

``` bash
$ service network restart
```

