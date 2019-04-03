# config

测试

## 客户端配置说明
```properties
spring:
  cloud:
    config:
      profile: dev
      label: user-service #Git服务器存储目录
      uri: http://localhost:8888
```

“name”= ${spring.application.name}
“profile”= ${spring.profiles.active}（实际上是Environment.getActiveProfiles()）
“label”=“master”

## SpringCloudConfig服务启动后访问规则
按照以下规则访问配置信息：
/{name}/{profile}/{label}
```
/ {application} / {profile} [ / {label} ]
/ {application} - {profile} . yml
/ {label} / {application} - {profile} . yml
/ {application} - {profile} . properties
/ {label} / {application} - {profile} . properties
```
