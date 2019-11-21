Error:Jack is required to support java 8 language features. Either enable Jack or remove sourceCompatibility JavaVersion.VERSION_1_8.
------------------

### 解决方案：

> 在 app 下的 build.gradle 文件中 添加如下代码：

```

android {

	.....
	
    compileOptions {
        sourceCompatibility JavaVersion.VERSION_1_8
        targetCompatibility JavaVersion.VERSION_1_8
    }
    
    .......
    
}


```