# idea plugin测试运行没问题 打包后进行导入安装发现group可见，action不可见.md

idea plugin测试运行没问题 打包后进行导入安装发现group可见，action不可见.md

原因是，因为编译该plugin的JDK为12，但是现在大部分的idea只支持jdk11进行运行，由于版本太高，无法运行成功。

解决方案：将本地的JDK移除，安装低于或等于11版本的JDK，更改idea的JDK版本，重新编译重新打包重新安装，即可。