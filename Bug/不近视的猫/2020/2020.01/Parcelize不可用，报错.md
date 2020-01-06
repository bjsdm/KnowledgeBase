# Parcelize不可用，报错

https://stackoverflow.com/questions/55772345/unresolved-reference-parcelize-after-updating-to-kotlin-1-3-30

其实就是把`apply plugin: 'kotlin-android'`和`apply plugin: 'kotlin-android-extensions'`进行换位置，位置换为：

```
apply plugin: 'com.android.application'
apply plugin: 'kotlin-android'
apply plugin: 'kotlin-android-extensions'
```