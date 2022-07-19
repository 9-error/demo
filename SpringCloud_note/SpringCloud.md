### 2.Eureka注册中心

#### 搭建EurekaServer

1. 创建Eureka项目模块，引入spring-cloud-starter-netfix-eureka-server依赖

   ```xml
    <dependency>
        <groupId>org.springframework.cloud</groupId>
        <artifactId>spring-cloud-starter-netflix-eureka-server</artifactId> 
    </dependency>
   ```

   

2. 编写启动类，添加@EnableEurekaServer注解

   ![eureka1](F:\zhu\project\SpringCloud\SpringCloud_note\SpringCloudAssets\eureka1.png)

   

3. 添加application.yml文件，编写配置

   ![eureka2](F:\zhu\project\SpringCloud\SpringCloud_note\SpringCloudAssets\eureka2.png)

   ```yaml
   server:
     port: 10086 #服务端口
   spring:
     application:
       name: eurekaserver #服务名称
   eureka:
     client:
       server-url:  
         defaultZone: http://127.0.0.1:10086/eurek #地址信息
      
   ```



#### 注册user-service

将user-service服务注册到EurekaServer步骤

1. 引入客户端依赖
2. 加入@EnableEurekaClient注解
3. 在application.yml文件下编写配置