WebView reload（）没效果
-------------

### 解决方案:

> 在用原生 WebVIew 像刷新页面，WebVIew 有提供一个 `reload（）`方法。但是实际使用时可能会没效果。一般使用加载方法就可以刷新页面了 `load（）`

```
webView.load(url);

```
