项目迁移 Android X
-------------

### 第一步：

> 在 `gradle.properties` 文件添加

```
android.useAndroidX=true
android.enableJetifier=true

```


### 第二步：

> 在项目根目录下的 `build.gradle` 升级 gradle 工具和 gradle 插件

```

buildscript {
    repositories {
        ...
    }
    dependencies {
        classpath 'com.android.tools.build:gradle:3.5.2'
        classpath 'com.github.dcendents:android-maven-gradle-plugin:2.1'
        ...
    }
}


```


### 第三步：

> 在 app 下的 `build.gralde` 升级 Android


- compileSdkVersion 版本升级到 28及以上
- buildToolsVersion 版本改为 28.0.2及以上


### 第四步：

> 使用 Android studio 的自动迁移功能。

![](https://upload-images.jianshu.io/upload_images/4625401-b9524e8fa789d620.png)


### 第五步：

> 这一步也是工作量最大的一步。就是把要去每个引用了 import support 包的 Java 文件和 XML 文件替换为 Android X 的引用。

[google 官方替换表](https://developer.android.google.cn/jetpack/androidx/migrate)

### 拓展阅读

[Android AndroidX的迁移](https://www.jianshu.com/p/7dc111353328)