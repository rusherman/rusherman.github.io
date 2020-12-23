1. 安装docker
2. 拉取tomcat镜像
3. 配置容器开启jpda调试
```shell
docker run -p 127.0.0.1:8082:8080 -p 127.0.0.1:5005:5005 -v /$WORKPATH/app_name/target/app_name:/usr/local/tomcat/webapps/ROOT --env TZ=Asia/Shanghai --env JPDA_ADDRESS=5005 --env JPDA_TRANSPORT=dt_socket --name company-store-manage tomcat:9.0.40-jdk8-adoptopenjdk-hotspot catalina.sh jpda run
```
4. 配置idea远程调试
![image.png](https://upload-images.jianshu.io/upload_images/10487206-82a2c623195d2e82.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
5.其他应用调试，以及springboot应用docker调试参考
https://www.jetbrains.com/help/idea/debug-a-java-application-using-a-dockerfile.html

