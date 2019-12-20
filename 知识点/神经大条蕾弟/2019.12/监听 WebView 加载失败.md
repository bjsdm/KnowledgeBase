监听 WebView 加载失败
-------------

### 解决方案:

> 在项目中经常会有需求监听 WebView 加载失败然后展示加载失败的页面。这些需要重写 WebViewClient 的方法


```

public abstract class BaseWebViewClient extends WebViewClient{

....

    @RequiresApi(api = Build.VERSION_CODES.M)
    @Override
    public void onReceivedError(WebView webView, WebResourceRequest request, WebResourceError error) {
        show404Dialog(webView, webView.getUrl(), false);
        LogUtil.e("网页加载失败onReceivedError:" + error.getDescription() + error.getErrorCode() + webView.getUrl());
    }

    @Override
    public void onReceivedSslError(WebView webView, SslErrorHandler handler, SslError error) {
        //Proceed with the SSL certificate.
        handler.proceed();
        show404Dialog(webView, webView.getUrl(), true);
        LogUtil.e("加载失败onReceivedSslError:" + webView.getUrl());
    }

    @Override
    public void onReceivedHttpError(final WebView webView, WebResourceRequest request, WebResourceResponse errorResponse) {
        super.onReceivedHttpError(webView, request, errorResponse);
        show404Dialog(webView, webView.getUrl(), true);
        LogUtil.e("加载失败onReceivedHttpError" + webView.getUrl());
    }
    @Override
    public void onReceivedError(WebView webView, int errorCode, String description, String failingUrl) {
        super.onReceivedError(webView, errorCode, description, failingUrl);
        show404Dialog(webView, webView.getUrl(), true);
        LogUtil.e("加载失败onReceivedError" + webView.getUrl());
    }


}


```