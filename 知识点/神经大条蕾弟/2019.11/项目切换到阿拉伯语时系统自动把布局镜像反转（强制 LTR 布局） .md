项目切换到阿拉伯语时系统自动把布局镜像反转（强制 LTR 布局）
---------------

### 解决方案：

> 在项目主题中加入 `<item name="android:layoutDirection">ltr</item>`


```

 <!-- Base application theme. -->
<style name="AppTheme" parent="Theme.AppCompat.Light.NoActionBar">
    <!-- Customize your theme here. -->
    .....
    .....
    <item name="android:layoutDirection">ltr</item>
</style>


```

### 拓展资料：

[StackOverFlow](https://stackoverflow.com/questions/39817683/forcing-the-app-to-work-as-ltr)