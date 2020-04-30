---
title: Python使用virtualenv搭建开发环境
date: 2018-07-02 14:45:35
categories:
- 编程语言
tags:
- Python
---


## 安装virtualenv

```bash
pip install virtualenv
```
或
新建一个requirement.txt,文件内容如下
```text
virtualenv
```

执行如下命令
```bash
pip install -r requirement.txt
```

如果网速太慢, 可使用豆瓣源加速,添加'-i 加速源URL'参数即可
例如: 
```bash
pip install -i https://pypi.douban.com/simple/ virtualenv
```
or
```bash
pip install -i https://pypi.douban.com/simple/ -r requirement.txt
```


## 新建环境

在当前目录下新建一个djangotest的虚拟环境
```bash
virtualenv djangotest
```

指定Python版本为Python3.6
```bash
virtualenv -p D:\Program Files\Python\Python36\python.exe djangotest1
```
