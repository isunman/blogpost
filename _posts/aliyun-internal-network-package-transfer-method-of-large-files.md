---
title: 阿里云内网打包传输较大文件的方法
tags: [Linux,远程控制]
categories: 服务器
date: 2020-11-13 15:15
---

今天老夫遇到一个将其一台阿里云ECS服务器某个目录下的所有文件迁移到另外一台服务器，原本以为是一个普通的操作，熟料到一看数据有10GB左右，打包压缩之后基本没有小多少，所以正常的常规wget下载肯定是不行的，效率太低，最快只有500KB/s左右。因此，在这里我准备采用阿里云自带的内网IP地址，然后直接内网SCP拖过去。

第一、准备工作

1、登录阿里云账户看到ECS服务器对应的内网IP地址。（打包文件的服务器内网IP）

2、打包压缩需要备份的网站目录，因为这里我开始打包过了，其实我不应该打包的，直接SCP，因为数据较大，打包时间也很长，后面还要解压也需要时间。

第二、SCP命令传输

1、复制目录到本地

    scp -r root@网站所在内网IP地址:/home/wwwroot/拷贝网站目录 /当前拷贝过来的网站目录

2、复制打包文件到本地

    scp root@网站所在的内网IP:/home/wwwroot/拷贝网站目录/laozuo.tar.gz /当前拷贝过来的网站目录

这个执行是在我们转入进来的服务器SSH执行，然后会要求我们同意和输入转出服务器的密码后开始传输。看来速度比直接wget快很多了，达到46MB/s。

最后，稍等几分钟（这里10G大概不到5分钟)，传输完毕之后我们再到服务器中解压和数据拷贝（移动）即可。

【注意】

如果当前用户登录在【目标主机】，从【源主机】拷贝到【目标主机】时，有问题的话（需要输入【源主机】用户SSH密码），

也可以反过来操作，即：用户登录到【源主机】，然后再从【源主机】拷贝到【目标主机】，需要输入【目标主机】的用户SSH密码。

    scp /root/yasm-1.3.0.tar.gz root@111.66.66.888:/root/

以上为一条具体的示例。

　　




