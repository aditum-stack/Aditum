<p align="center">
  <img src="https://github.com/kevinten10/Aditum/blob/master/logo.png" style="height:200px"/>
</p>

# Aditum - community access control big data analysis system based on distributed architecture

<p align="center">
  <img src="https://img.shields.io/github/license/mashape/apistatus.svg" alt="license"/>
</p>

## Introduction

community access control big data analysis system based on distributed architecture

## Technology Stack

####基础设施分析

拟将采用3台物理服务器搭建分布式环境或采用本地伪分布式环境，操作系统采用Linux(centos环境)，数据库采用MySQL，HBASE，以及MongoDB。
基于Hadoop搭建HDFS分布式文件系统，并通过HTTP协议/RESTful风格进行服务间通信。

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
  <img src="https://github.com/kevinten10/Aditum/blob/master/微服务架构.JPG" />
</p>

#### Aditum大数据平台架构

<p align="center">
  <img src="https://github.com/kevinten10/Aditum/blob/master/大数据平台架构.JPG" />
</p>

## Service

#### Aditum微服务运行流程

<p align="center">
  <img src="https://github.com/kevinten10/Aditum/blob/master/微服务运行流程.JPG" />
</p>

#### Mocker

<p align="center">
  <img src="https://github.com/kevinten10/Aditum/blob/master/Aditum流程图/Mocker.PNG" />
</p>

#### Collector

<p align="center">
  <img src="https://github.com/kevinten10/Aditum/blob/master/Aditum流程图/Collector.PNG" />
</p>

#### Logger

<p align="center">
  <img src="https://github.com/kevinten10/Aditum/blob/master/Aditum流程图/Logger.PNG" />
</p>

#### Statistics

<p align="center">
  <img src="https://github.com/kevinten10/Aditum/blob/master/Aditum流程图/Statistics.PNG" />
</p>

#### Personas

<p align="center">
  <img src="https://github.com/kevinten10/Aditum/blob/master/Aditum流程图/Personas.PNG" />
</p>

## License

Copyright (c) 2018-present kevinten10



