获取 WebView 中的网页标题
-------------

### 解决方案:

> 在混合开发中又可能碰到需要标题栏是原生的，内容是 H5的。所以需要我们原生去获取 H5 的标题。就需要重写 WebChromeClient 的 `onReceivedTitle()` 方法。

```
public abstract class BaseWebChromeClient extends WebChromeClient {

    .....

    /**
     * 获取网页标题
     *
     * @param view
     * @param title
     */
    @Override
    public void onReceivedTitle(WebView view, String title) {
        super.onReceivedTitle(view, title);
        setTitle(title);
    }


```
