---
layout: post
title: 在 Centos7 安装 JDK8
category: actual-combat
tags: [actual-combat]
excerpt: 详细介绍在Centos7上安装JDK8的步骤，并且提供JDK8的下载
---

## 01 下载 JDK

大家可以选择去 Oracle 官网选择对应的 JDK 版本自主 [下载](https://www.oracle.com/java/technologies/javase-downloads.html) ，当然也可以使用笔者准备好的 JDK8 ，[点我](https://pan.baidu.com/s/1CRggR0Joshz9P8pw3sZ6DA)，提取码为：4ykp 。



## 02 上传 JDK 到 Centos7

通过 WinSCP 工具将 JDK8 tar 包上传到服务器，提供 WinSCP 文件上传工具的下载链接，[点我](https://pan.baidu.com/s/1KjfomDf0VBvx8VaguWM4nA)，提取码：r5se 。

首先在Centos7创建文件夹。

```shell
mkdir /usr/java
cd /usr/java
```

将 JDK8 tar 包，通过WinSCP工具上传到 /usr/java。

![](https://markdown-chenrong.oss-cn-shenzhen.aliyuncs.com/actual-combat/55513897676e47fd953c4be801df187.png)



## 03 解压 JDK8 tar 包

```shell
tar -zxvf jdk-8u191-linux-x64.tar.gz
```

解压好后的效果如下：

![](https://markdown-chenrong.oss-cn-shenzhen.aliyuncs.com/actual-combat/1592295571%281%29.png)



## 04 配置 JDK 环境变量

```shell
cd jdk1.8.0_191/
pwd
vim /etc/profile
```

修改 profile 配置文件，首先输入 i 进入编辑状态，再将光标移到文件尾部，在文件的尾部添加如下的内容：

```shell
# java jdk
JAVA_HOME=/usr/java/jdk1.8.0_191
CLASSPATH=$JAVA_HOME/lib/
PATH=$PATH:$JAVA_HOME/bin
export PATH JAVA_HOME CLASSPATH
```

修改profile文件后的效果如下：

![](https://markdown-chenrong.oss-cn-shenzhen.aliyuncs.com/actual-combat/1592296505.png)

点击 esc 进入命令模式， 输入：wq 保存修改信息。

最后重新加载 profile 配置文件。

```shell
source /etc/profile
```



## 05 测试 JDK8 的安装效果

```shell
java -version
```

JDK8 安装成功的效果图如下：

![](https://markdown-chenrong.oss-cn-shenzhen.aliyuncs.com/actual-combat/1592296913%281%29.png)



若在 Centos7 安装 JDK8 的过程中出现任何问题，欢迎留言提问~~