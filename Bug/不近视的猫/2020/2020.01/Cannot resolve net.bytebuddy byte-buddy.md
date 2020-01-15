# Cannot resolve net.bytebuddy:byte-buddy

第一次使用 Springboot 的时候，报以下错误

```
Cannot resolve net.bytebuddy:byte-buddy 1.10.4
```

解决方案：

在`pom.xml`文件中，加入：

```
        <!-- https://mvnrepository.com/artifact/net.bytebuddy/byte-buddy-agent -->
        <dependency>
            <groupId>net.bytebuddy</groupId>
            <artifactId>byte-buddy-agent</artifactId>
            <version>1.10.6</version>
            <scope>test</scope>
        </dependency>
        <!-- https://mvnrepository.com/artifact/net.bytebuddy/byte-buddy -->
        <dependency>
            <groupId>net.bytebuddy</groupId>
            <artifactId>byte-buddy</artifactId>
            <version>1.10.6</version>
        </dependency>
```

详情参考以下网址：

https://blog.csdn.net/weixin_43748192/article/details/98970558