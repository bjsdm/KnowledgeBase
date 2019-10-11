## 沉浸式状态栏下,EditText被软键盘覆盖问题

### AndroidBug5497Workaround
```java
public class AndroidBug5497Workaround {  
  /*  
 * 作者：随手记技术团队  
 链接：https://juejin.im/post/5a25f6146fb9a0452405ad5b*/  
  public static void assistActivity(View content) {  
  new AndroidBug5497Workaround(content);  
 }  
  private View mChildOfContent;  
  private int usableHeightPrevious;  
  private ViewGroup.LayoutParams frameLayoutParams;  
  
  private AndroidBug5497Workaround(View content) {  
  if (content != null) {  
  mChildOfContent = content;  
  mChildOfContent.getViewTreeObserver().addOnGlobalLayoutListener(new ViewTreeObserver.OnGlobalLayoutListener() {  
  @Override  
  public void onGlobalLayout() {  
  possiblyResizeChildOfContent();  
 } });  frameLayoutParams = mChildOfContent.getLayoutParams();  
 } }  
  private void possiblyResizeChildOfContent() {  
  int usableHeightNow = computeUsableHeight();  
  if (usableHeightNow != usableHeightPrevious) {  
  //如果两次高度不一致  
  //将计算的可视高度设置成视图的高度  
  frameLayoutParams.height = usableHeightNow;  
  mChildOfContent.requestLayout();//请求重新布局  
  usableHeightPrevious = usableHeightNow;  
 } }  
  private int computeUsableHeight() {  
  //计算视图可视高度  
  Rect r = new Rect();  
  mChildOfContent.getWindowVisibleDisplayFrame(r);  
  return r.bottom;  
 }  
}
```
### 私聊Activity

```java
@Override  
protected void initTitle() {  
  hideStatusBar();  
  hideTitleBar();  
  setStatusBarBlackFont();  
  AndroidBug5497Workaround.assistActivity(findViewById(android.R.id.content));  
}
```
