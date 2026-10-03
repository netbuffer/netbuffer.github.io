---
title: spring-cloud-demo
date: 2020-09-17
tags:
  - Spring Cloud
  - Java
  - 微服务
categories:
  - Spring Cloud
cover: /img/post-spring-cloud.jpg
top_img: /img/post-spring-cloud.jpg
---

Spring Cloud 微服务架构实战 Demo，涵盖服务注册发现（Eureka）、负载均衡（Ribbon）、熔断降级（Hystrix）、API 网关（Zuul）等核心组件的完整集成示例。

<!-- more -->

## 项目结构

```bash
spring-cloud-demo/
├── eureka-server      # 注册中心
├── api-gateway        # 网关
├── service-provider   # 服务提供者
└── service-consumer   # 服务消费者
```

## 技术选型

- Spring Boot 2.3.x
- Spring Cloud Hoxton.SR8
- Eureka 服务注册发现
- Ribbon 负载均衡
- Feign 声明式 HTTP 客户端
- Hystrix 熔断降级
