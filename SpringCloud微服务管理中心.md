# Spring Cloud 框架下的微服务管理中心的搭建

|模块|功能|环境|端口号|
|---|---|---|---|
|Eureka-Server|服务注册中心服务端|生产|10001
|Gateway-Zuul|服务API网关服务|生产|10002
|Hystrix-Dashboard|服务状态监控器|生产-监控|10003
|Eureka-Client|服务注册中心客户端|测试Eureka注册服务|20001
|Consume-Service|服务消费者|测试微服务流程-调用服务|20002
|Produce-Service|服务生产者|测试微服务流程-提供服务|20003

## 启动流程

1. 启动 Eureka-Server 服务注册中心
2. 启动其他服务（顺序任意，但推荐先启动生产项目）
3. 浏览器输入 localhost:20002/consume/{任意字符串} 即刻访问 Consume-Service 调用 Produce-Service 的返回结果
4. 输入 http://localhost:10003/hystrix 进入监控中心

## 需求分析

为Aditum微服务架构提供一个管理平台，首先采用单机云服务器部署，能够通过http维护管理所有的Aditum微服务

## Config服务配置客户端

采用Apollo实现配置中心服务端，替代springcloud-config，在此项目中不再进行config服务端实现。

同时，此项目中的各个配置项，首先采用本地resources文件进行开发。

开发通过后，在正式环境中，将通过apollo服务进行获取，不再写入到resources文件中。

由于apollo对properties文件支持好，将使用properties文件替代yml文件。

apollo配置中心地址：ip:[8070]/[8080]/[8090]

## Eureka服务注册中心

实现springcloud-eureka服务端，各个微服务通过http进行服务注册发现。

Eureka服务发现中心地址：http://${eureka.instance.hostname}:${server.port}/eureka/

## Hystrix DashBoard监控平台使用

引入相关依赖，启用 @EnableHystrixDashboard （好像还需要@EnableCircuitBreaker）注解，通过引入监控的项目 ip:port/hystrix 访问，然后输入 ip:port/hystrix.stream 进行监控

## Zuul API网关

API网关是一个服务器，可以说是进入系统的唯一节点，封装了内部系统的架构，并且提供了API给各个客户端。

负责请求转发、合成、协议转换。先网关，在负载均衡到对应的微服务。

--------------------------------------------------------------

# 客户端

## Eureka客户端

通过类RestTemplate进行服务调用，可使用 服务名/服务ip地址 进行接口调用

注意，依赖是 eureka-server 那一个，而不是 eureka-client 那一个

## Ribbon负载均衡

通过在RestTemplate类上注解 @LoadBalanced 即可实现负载均衡（注解已包含在Eureka客户端中）

## Hystrix服务熔断

需要额外引入hystrix依赖，使用 @EnableCircuitBreaker 开启断路器功能

在远程调用方法上使用 @HystrixCommand(fallbackMethod = 断路方法名) 进行异常时逻辑处理

例如：func : {return "服务不可用，请稍后再试！"} 