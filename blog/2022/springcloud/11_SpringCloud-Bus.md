---
title: SpringCloud-Bus分布式节点链接
author: mykk
top: false
cover: false
toc: true
mathjax: false
summary: Spring Cloud Bus是用来将分布式系统的节点与轻量级消息系统链接起来的框架
tags:
  - springcloud
  - bus
  - 节点链接
categories:
  - 分布式技术栈
abbrlink: 
reprintPolicy: cc_by
date: 2022-02-06 11:49:12
coverImg:
img:
password:
---



## 1、概述

### 1、是什么

Bus支持两种消息代理：RabbitMQ 和 Kafka



Spring Cloud Bus 配合 Spring Cloud Config 使用可以实现配置的动态刷新。

![](https://cdn.jsdelivr.net/gh/mykkTo/image@main/blog/2022/springcloud/20220208124710.png)



Spring Cloud Bus是用来将分布式系统的节点与轻量级消息系统链接起来的框架，
`它整合了Java的事件处理机制和消息中间件的功能`。

Spring Clud Bus目前支持RabbitMQ和Kafka。

### 2、能干嘛

Spring Cloud Bus能管理和传播分布式系统间的消息，就像一个分布式执行器，可用于广播状态更改、事件推送等，也可以当作微服务间的通信通道。



### 3、为何被称为总线



#### 什么是总线

在微服务架构的系统中，通常会使用轻量级的消息代理来构建一个共用的消息主题，并让系统中所有微服务实例都连接上来。由于该主题中产生的消息会被所有实例监听和消费，所以称它为消息总线。在总线上的各个实例，都可以方便地广播一些需要让其他连接在该主题上的实例都知道的消息。



#### 基本原理

ConfigClient实例都监听MQ中同一个topic(默认是springCloudBus)。当一个服务刷新数据的时候，它会把这个信息放入到Topic中，这样其它监听同一Topic的服务就能得到通知，然后去更新自身的配置。



## 2、RabbitMQ环境配置

### 1、安装

安装docker：https://www.jianshu.com/p/f554c85b25c1

#### 1、拉取

`docker pull  rabbitmq:3.7.7-management`

#### 2、创建容器并启动

`docker run -d --hostname localhost --name myrabbit -p 15672:15672 -p 5672:5672 rabbitmq:3.7.7-management`



- -d 后台运行容器；

- --name 指定容器名；

- -p 指定服务运行的端口（5672：应用访问端口；15672：控制台Web端口号）；

- -v 映射目录或文件；

- --hostname  主机名（RabbitMQ的一个重要注意事项是它根据所谓的 “节点名称” 存储数据，默认为主机名）；

- -e 指定环境变量；
  - 默认的用户名：`guest`；
  - 默认用户名的密码：`guest`）

#### 3、访问

http://localhost:15672/  （换成自己服务器的IP）

![](https://cdn.jsdelivr.net/gh/mykkTo/image@main/blog/2022/springcloud/20220208150738.png)



## 3、SpringCloud Bus动态刷新全局广播

### 1、

### 2、

### 3、

### 4、

### 5、

## 4、SpringCloud Bus动态刷新定点通知

### 1、

### 2、

### 3、

### 4、

### 5、





## 参考：

https://blog.csdn.net/haoweng4800/article/details/102946846

https://www.cnblogs.com/huanshilang/p/12585877.html

https://www.jianshu.com/p/efac7bd8941f