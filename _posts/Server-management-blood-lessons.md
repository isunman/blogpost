---
title: 服务器管理血的教训
tags: [Linux]
categories: 服务器
date: 2021-04-25 05:38
---

服务器管理血的教训

服务器管理，尤其是Linux服务器管理，必须注意以下几项原则，并做到。

### 1、绝对不能随便使用`rm -rf`命令
因为会递归强制删除文件，几乎都不会可恢复。【影响响程度太深】
##### 挽救措施：

1、马上停止数据继续写入，将系统挂起。使用一些恢复数据的方法进行磁盘数据数据恢复操作。一般不能全部恢复；而且还会影响线上的业务的停止。

2、把快照的数据恢复到一个其他不是生产环境的阿里云服务器实例上，然后恢复到那个快照中的数据，再把误删除而需要的数据拷贝过来。原线上生产环境的业务不用停止。

### 2、绝对不能使用 `yum update`命令
因为会升级Linux 内核，而这个升级后的内核可能会引起各种问题。【影响范围太大】

##### 挽救措施：
如果之前的系统内核还在，重启启动那个内核；
如果没问题的话，设置开机启动的内核为这个正常可用的内核。

### 3、关键操作开始之前必须备份数据+快照

既不能因为精神不好产生错误的指令输入，或者粗心大意没有在意造成严重的后果；
又不能怕操作错误而什么都不敢做了。

有一个宗旨【稳定第一】【宁愿冗余，也不得丢失数据】。

不明确知道命令输入执行的后果的，就绝不执行。


——————于2021年04月25日 凌晨5：35——必须记下。


