---
title: Xcode中的Version和Build的区别
tags: [iOS]
categories: iOS
date: 2018-08-01 23:17
---


### Version对应的是CFBundleShortVersionString。
Version 一般由产品部门确定，版本号是由分隔的整数组成的字符串，一般有2段或者3段式, 如:1.2,  1.2.3

### 二段式：

第一个段：（主版本号）大功能的新增或者有迥异的变化
第二个段：（副版本号）既包含小功能更新也会包含 bug 修复

### 三段式：

第一个段：重大修改的版本，如实现新的大功能或重大变化的修订。
第二个段：实现较突出的特点，如新功能添加和大问题修复。
第三个段：代表维护版本，修复bug。

**版本号的管理是一个谨慎的事情，希望各位开发者了解其中的意义。**

### Build（ 应用程序内部标示 ）

Bulid 是给内部使用,与 Version 不会有太大联系.

Bulid对应的是CFBundleVersion。标识（发布或未发布）的内部版本号。用以记录开发版本的，每次更新的时候都需要比上一次高。
作用：发布build版本供测试团队进行测试。

