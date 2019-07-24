---
layout:     post
title:      python pip使用国内镜像
subtitle:   python pip
date:       2019-7-24
author:     maomaochen/部分转载
header-img: img/post-bg-rwd.jpg
keywords_post:  "python"
catalog: true
tags:
    - python
---

python用pip安装库时，会从python官方源下载，有时速度很慢，浪费时间还容易出错。将pip安装源替换为国内镜像可以大幅提升下载速度，提高安装成功率。

## 国内源

清华：https://pypi.tuna.tsinghua.edu.cn/simple

阿里云：http://mirrors.aliyun.com/pypi/simple/

中国科技大学：https://pypi.mirrors.ustc.edu.cn/simple/

华中理工大学：http://pypi.hustunique.com/

山东理工大学：http://pypi.sdutlinux.org/ 

豆瓣：http://pypi.douban.com/simple/

*note：新版ubuntu要求使用https源，要注意。*

## 临时使用

可以在使用pip的时候加参数`-i https://pypi.tuna.tsinghua.edu.cn/simple`。

例如：`pip install -i https://pypi.tuna.tsinghua.edu.cn/simple pyspider`，这样就会从清华这边的镜像去安装`pyspider`库。

## 永久修改

### windows

在`C:\User\用户名\`目录下创建`pip`目录，`pip`目录下创建`pip.ini`文件，以`UTF-8无BOM格式编码`。

文件内容如下：

```c++
[global]
index-url = http://mirrors.aliyun.com/pypi/simple/
[install]
trusted-host = mirrors.aliyun.com
```

**注意：**trusted-host选项是为了避免麻烦，否则使用时会提示不受信任，或者添加`--trusted-host = mirrors.aliyun.com`选项。

### Linux

修改`~/.pip/pip.conf`，没有就创建一个，文件夹要加`.`，表示是隐藏文件夹，文件内容同windows。



以前Anaconda也可以使用国内的镜像，不过近期国内镜像陆续停止了对Anaconda的服务。

> 参考：https://www.cnblogs.com/microman/p/6107879.html



<br>