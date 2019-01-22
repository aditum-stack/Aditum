<p align="center">
  <img src="https://github.com/kevinten10/Aditum/blob/master/aditum-doc/logo.png" style="height:200px"/>
</p>

# Aditum - community access control big data analysis system based on distributed architecture

<p align="center">
  <img src="https://img.shields.io/github/license/mashape/apistatus.svg" alt="license"/>
</p>

## Introduction

community access control big data analysis system based on distributed architecture

## Technology Stack

#### 基础设施分析
 
1. 服务器基于Linux(centos)系统。
2. 通过容器技术部署微服务。
3. 数据库采用MySQL，HBASE，以及MongoDB。
4. 基于Hadoop搭建HDFS分布式文件系统。
5. 通过REST HTTP协议进行服务间通信。
 
#### 开发语言

使用Java语言进行主要微服务的构架，以及Hadoop相关框架的开发。

使用Scala语言进行Spark计算引擎编程，进行统计分析计算。

使用Python语言机器学习库进行用户画像k-means聚类算法的数据分析。

## Projects

*	Cloud微服务架构 [Aditum-Cloud](https://github.com/kevinten10/Aditum-Cloud)

*	Config云配置中心 [Aditum-Config](https://github.com/kevinten10/Aditum-Config)

*	Mocker数据模拟服务 [Aditum-Mocker](https://github.com/kevinten10/Aditum-Mocker)

*	Collector数据聚合服务 [Aditum-Collector](https://github.com/kevinten10/Aditum-Collector)

*	Logger日志清洗服务 [Aditum-Logger](https://github.com/kevinten10/Aditum-Logger)

*	Statistics统计分析服务 [Aditum-Statistics](https://github.com/kevinten10/Aditum-Statistics)

*	Personas用户画像分析服务 [Aditum-Personas](https://github.com/kevinten10/Aditum-Personas)

*	RESTful后端数据交互服务 [Aditum-Back](https://github.com/kevinten10/Aditum-Back)

*	Vuejs前端WEB展示站点 [Aditum-Web](https://github.com/kevinten10/Aditum-Web)

## Architecture

#### Aditum微服务架构

<p align="center">
  <img src="https://github.com/kevinten10/Aditum/blob/master/aditum-doc/微服务架构.JPG" />
</p>

#### Aditum大数据平台架构

<p align="center">
  <img src="https://github.com/kevinten10/Aditum/blob/master/aditum-doc/大数据平台架构.JPG" />
</p>

## Service

#### Aditum微服务运行流程

<p align="center">
  <img src="https://github.com/kevinten10/Aditum/blob/master/aditum-doc/微服务运行流程.JPG" />
</p>

#### Mocker

<p align="center">
  <img src="https://github.com/kevinten10/Aditum/blob/master/aditum-doc/Aditum流程图/Mocker.PNG" />
</p>

    拟采用编程语言：Java
    
    主要技术分析：
    
    Quartz定时调度框架
    
    多线程调度
    
    确保数据合理性
    
    生成模拟数据库
    
    生成模拟日志

#### Collector

<p align="center">
  <img src="https://github.com/kevinten10/Aditum/blob/master/aditum-doc/Aditum流程图/Collector.PNG" />
</p>

    拟采用编程语言：Java
    
    主要技术分析：
    
    Flume日志聚合
    
    Kafka消息队列
    
    HDFS分布式文件系统
    
    HBASE分布式数据库

#### Logger

<p align="center">
  <img src="https://github.com/kevinten10/Aditum/blob/master/aditum-doc/Aditum流程图/Logger.PNG" />
</p>

    拟采用编程语言：Java
    
    主要技术分析：
    
    日志清洗规则建模
    
    数据匹配工具
    
    Kafka消息队列消费

#### Statistics

<p align="center">
  <img src="https://github.com/kevinten10/Aditum/blob/master/aditum-doc/Aditum流程图/Statistics.PNG" />
</p>

    拟采用编程语言：Scala
    
    主要技术分析：
    
    Spark计算引擎编程
    
    Spark多任务调度
    
    RDD弹性数据集处理
    
    数据结构化建模

#### Personas

<p align="center">
  <img src="https://github.com/kevinten10/Aditum/blob/master/aditum-doc/Aditum流程图/Personas.PNG" />
</p>

    拟采用编程语言：Python
    
    主要技术分析：
    
    k-means聚类算法
    
    用户画像标签建模
    
    python多线程调度
    
    MongoDB数据库存储

## License

Copyright (c) 2018-present kevinten10



