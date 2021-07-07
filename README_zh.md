# fofa-spring-boot-starter

[![GitHub (pre-)release](https://img.shields.io/github/release/0nise/fofa-spring-boot-starter/all.svg)](https://github.com/0nise/fofa-java/releases)
[![stars](https://img.shields.io/github/stars/0nise/fofa-spring-boot-starter.svg)](https://github.com/0nise/fofa-java/stargazers)
[![license](https://img.shields.io/github/license/0nise/fofa-spring-boot-starter.svg)](https://github.com/0nise/fofa-java/blob/master/LICENSE)

[English document](https://github.com/0nise/fofa-spring-boot-starter/blob/master/README.md)

## FOFA Pro API
[`FOFA Pro API`](https://fofa.so/api) 是资产搜索引擎 [`FOFA Pro`](https://fofa.so) 为开发者提供的 `RESTful API` 接口, 允许开发者在自己的项目中集成 [`FOFA Pro`](https://fofa.so) 的功能。

## FOFA SDK

基于 [`FOFA Pro API`](https://fofa.so/api) 编写的 `Spring Boot` 版 `SDK`, 方便 java 开发者快速将 [`FOFA Pro`](https://fofa.so) 集成到自己的项目中。

## 添加依赖

### Apache Maven

```java
<dependency>
  <groupId>com.r4v3zn.fofa</groupId>
  <artifactId>fofa-spring-boot-starter</artifactId>
  <version>1.0.4</version>
</dependency>
```

### Gradle Groovy DSL

```java
implementation 'com.r4v3zn.fofa:fofa-spring-boot-starter:1.0.3'
```

### Gradle Kotlin DSL

```java
compile("com.r4v3zn.fofa:fofa-spring-boot-starter:1.0.3")
```

### Scala SBT

```java
libraryDependencies += "com.r4v3zn.fofa" % "fofa-spring-boot-starter" % "1.0.3"
```

### Apache Ivy

```java
<dependency org="com.r4v3zn.fofa" name="fofa-spring-boot-starter" rev="1.0.3" />
```

### Groovy Grape

```java
@Grapes(
  @Grab(group='com.r4v3zn.fofa', module='fofa-spring-boot-starter', version='1.0.3')
)
```

### Leiningen

```java
[com.r4v3zn.fofa/fofa-spring-boot-starter "1.0.3"]
```

### Apache Buildr

```java
'com.r4v3zn.fofa:fofa-spring-boot-starter:jar:1.0.3'
```

### Maven Central Badge

```java
[![Maven Central](https://img.shields.io/maven-central/v/com.r4v3zn.fofa/fofa-spring-boot-starter.svg?label=Maven%20Central)](https://search.maven.org/search?q=g:%22com.r4v3zn.fofa%22%20AND%20a:%22fofa-spring-boot-starter%22)
```

### PURL

```java
pkg:maven/com.r4v3zn.fofa/fofa-spring-boot-starter@1.0.3
```

### Bazel

```java
maven_jar(
    name = "fofa-spring-boot-starter",
    artifact = "com.r4v3zn.fofa:fofa-spring-boot-starter:1.0.3",
    sha1 = "eb6ae92fcb15ceba8833e5af8965fc5e96f840da",
)
```

## 使用

|字段名称|描述|
|:---------:|:-----------------:|
| `email` |用户登陆 [`FOFA Pro`](https://fofa.so) 使用的 `Email`|
|`key`| 前往 [`个人中心`](https://fofa.so/user/users/info) 查看 `API Key`|

### 配置

需要配置项目中的`application.yml`或`application.properties`文件。

#### application.yml
```yaml
fofa:
  email: 
  key: 
```
#### application.properties
```properties
fofa.email=
fofa.key=
```

### 获取用户信息

```java
@Autowired
private FofaClient client;

public String test() throws Exception {
    System.out.println(client.getUser());
    return "hello";
}
```

### 获取FOFA Pro 搜索结果

#### 代码

```java
@Autowired
private FofaClient client;

public String test() throws Exception {
    String q = "app=\"Solr\"";
    System.out.println(client.getData(q));
    return "hello";
}
```

#### 响应

```java
FofaData{mode='extended', page=1, size=8578, totalPage=86, query='app="Solr"', results=[52.204.201.10:8080, 39.106.133.253:8081, 168.61.45.247:3000, 185.145.32.101:9090, 47.92.153.193:8083, https://54.177.198.16:9443, https://46.137.115.176, 109.202.145.150:9090, 18.229.36.175, https://52.65.18.222, 94.103.24.81, 128.119.168.198:8080, 45.56.107.121:8090, 159.65.33.96:8080, 165.28.246.132, 34.205.15.100:8080, 3.89.155.86, 101.200.142.15:8099, 45.56.91.166:8090, 107.21.102.229, 89.28.161.145:8083, 35.165.137.220, 162.243.2.73:32768, 3.82.255.95:8080, 52.22.6.26, 96.126.97.74:8090, https://solr.swoonery.com, 63.34.225.181:8083, 18.223.238.90:7777, 167.99.252.65:8081, 18.232.114.197, 96.126.104.116:8090, 52.17.255.254, 101.201.145.141:8888, 13.228.98.189, 52.66.197.212:8081, 34.226.45.218:9443, 36.111.196.193:8082, 52.80.87.182, 97.107.133.44:8090, 173.255.217.135:8080, 34.199.97.120:8081, 52.17.131.156, https://13.55.200.182:443, 23.23.104.210, 54.68.95.160, https://54.77.13.29:8082, 66.175.209.109:8090, 52.200.107.211:8080, 104.130.124.46:7777, 192.231.177.172:8090, 54.221.155.2, 203.135.191.199:8080, 218.93.127.8:9080, 101.251.241.194:8081, 115.79.204.120:8888, 39.106.23.13:8180, https://52.16.231.131:8080, 52.5.53.165:8080, 39.106.180.220:8180, 52.67.86.138, https://52.26.130.143, 52.37.105.68, 23.239.19.16:8090, 52.58.193.2, 168.218.15.134, 52.44.108.125:9443, 76.210.250.82:32768, 52.71.163.53, 92.243.20.10:8080, 157.249.39.129, www.marineparts.us:8983, 185.135.12.139:8080, 123.207.239.114:8082, 66.175.209.253:8090, 66.175.209.38:8090, 173.255.223.210:8090, 14.29.118.239:20000, 70.142.24.61:8080, 3.87.173.6:8001, 47.107.106.243:20000, 101.201.117.191, 118.190.215.162, 116.203.141.150:8080, 58.250.149.11:8085, 3.88.123.255, 173.255.216.58:8090, 14.139.13.78:8080, 54.149.94.198, 142.93.183.248:8082, 216.47.157.209:8090, 202.202.240.113:7777, 198.101.238.25:8080, 52.66.72.8:8888, 92.243.20.10:8081, 23.239.23.20:8090, 39.107.94.23:8888, 79.137.82.228:8083, 120.55.191.189:8010, 52.21.16.23:8080]}
```

## 更新日志

2020-04-27

    - 升级 `fofa-java ` 版本至 `1.0.2.RELEASE`

2019-06-17

    - 开源
