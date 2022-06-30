### Image containing all Flowable UI apps running on Tomcat (with a in memory H2 database). 
- https://hub.docker.com/r/flowable/all-in-one


还可以使用这个：
- https://hub.docker.com/r/flowable/flowable-idm
- https://hub.docker.com/r/flowable/flowable-admin


```
sudo docker run -p8080:8080 flowable/flowable-idm

sudo docker run -p9988:9988 -e FLOWABLE_COMMON_APP_IDM-URL=http://192.168.17.129:8080/flowable-idm -e FLOWABLE_COMMON_APP_IDM-ADMIN_USER=admin -e FLOWABLE_COMMON_APP_IDM-ADMIN_PASSWORD=test flowable/flowable-admin
```



### Ref
- [推荐两个工作流的springboot项目](https://mp.weixin.qq.com/s/zKjAuxMATGN0BzD427EPlA)
- [【第一篇】Flowable的基本操作](https://dpb-bobokaoya-sm.blog.csdn.net/article/details/123522470)
- [【第八篇】Flowable之流程变量](https://blog.csdn.net/qq_38526573/article/details/123842772)
- https://gitee.com/shenzhanwang/Spring-activiti
- https://gitee.com/tony2y/RuoYi-flowable
- https://forum.flowable.org/t/how-to-write-a-custom-function-usable-in-juel-expressions/1844


### 配置
项目：https://gitee.com/tony2y/RuoYi-flowable
在pom.xml中设置依赖：
```xml
<dependency>
    <groupId>org.flowable</groupId>
    <artifactId>flowable-engine</artifactId>
    <version>6.3.0</version>
</dependency>
```

所需条件：
- localhost开启redis
- 修改ruoyi-admin/src/main/resources/application-druid.yml中的jdbc连接
- 修改ruoyi-admin/src/main/resources/application.yml中的redis密码
- 创建一个新的数据库ry_6_7_2，并source flowable.sql, quartz.sql, system.sql

执行命令：
```
java -jar ./ruoyi-admin/target/ruoyi-admin.jar
```