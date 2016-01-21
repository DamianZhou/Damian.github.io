---
layout            : post
title             : "Mac使用Fusion安装CentOS"
date              : 2015-12-13
categories        : [Software Skills]
tags              : [Software,MAC]
comments          : true # enable disqus comment
---

* content
{:toc}

####错误描述

直接从 WMware Fusion 中的`从光盘或映像安装`中选择ISO文件，然后按顺序安装CentOS，最后会卡在“installing VMware Tools”无法继续安装：

{% highlight bash %}
...
installing VMware Tools, please wait...
mount: special device /dev/hda does not exist
mount: block device /dev/sr0 is write-protected, mounting read only
/etc/rc5.d/S99local: line 25: eject: command not found
/etc/rc5.d/S99local: line 25: eject: command not found
{% endhighlight %}

软件环境如下

1. WMware Fusion 专业版 7.1.0 (2314774)
2. CentOS 6.6 64位

####正确安装方式

1. 选择`更多选项`
2. 在`创建自定虚拟机`中，选择Linux，并选中 **CentOS64位**，然后`继续`
3. 选择**新建虚拟磁盘**，然后`继续`
4. 点击`自定设置`，在弹出的窗口中修改文件名，然后点击`存储`。之后会跳出虚拟机的设置界面。
5. 在**可移除设备**这一行，选择`CD/DVD(IDE)`，然后选择一个要安装的CentOS的ISO文件。
6. 在**其他**这一行，点击`启动磁盘`，然后选择`CD/DVD`，并点击`重新启动`

接下来就是CentOS的正常安装过程。
>CentOS安装过程可以参考 [http://www.jb51.net/os/239738.html](http://www.jb51.net/os/239738.html)

最后安装完以后，将启动磁盘设置为`恢复默认`即可。

####参考

[https://www.centos.org/forums/viewtopic.php?t=4344](https://www.centos.org/forums/viewtopic.php?t=4344)

don't install centos directly when you create new vm on vmware.
here is step how to fix your problem.

1. create new vm on vmware an choose install operating system later.
2. make sure to mounting your installer (physical disc or iso file).
 a. right click on your new vm, select settings
 b. pointing to CD/DVD (IDE). select your installer on there (physical disc or iso file)
3. run it your vm, the installation will proceed using gui mode and the error messages doesn't appear
