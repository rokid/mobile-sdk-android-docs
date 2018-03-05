# RKWebBridge
## 快速接入
我们 提供了 封装好的 SDKWebviewClient、SDKWebview，方便开发者集成，请安装下面 Demo 代码使用即可，具体 Native UI 组件可根据APP业务需求进行实现。

DemoWebViewClient:

```Java
public class DemoWebViewClient extends SDKWebviewClient {

    public DemoWebViewClient(RKWebBridge webBridge) {
        super(webBridge);
    }
    
}
```

DemoWebView:

```Java

public class DemoWebView extends SDKWebview {

    private void init(Context context) {
        this.setWebViewClient(new DemoWebViewClient(webBridge));
        // ...
    }
    
    // 关闭当前页面
    @Override
    public void close() {
    }

    // 在当前的 webview ，打开Url
    @Override
    public void open(String title, String url) {
    }

    // 在一个新的 Activity 中打开Url
    @Override
    public void openNewWebView(String title, String url) {
    }
    
    // 使用外部浏览器 打开Url
    @Override
    public void openExternal(String url) {
    }

    // 显示 Toast
    @Override
    public void showToast(String message) {
    }

    // 显示 加载中UI组件
    @Override
    public void showLoading(String message) {
    }

    // 隐藏 加载中UI组件
    @Override
    public void hideLoading() {
    }

    // 设置 标题栏标题
    @Override
    public void setTitle(String title) {
    }

    // 设置 标题栏风格
    @Override
    public void setTitleBarStyle(String style) {
    }

    // 设置 标题栏 右侧按钮
    @Override
    public void setTitleBarRight(TitleBarButton titleBarButton){
    }

    // 设置 标题栏 右侧按钮小红点状态
    @Override
    public void setTitleBarRightDotState(boolean state) {
    }

    // 显示 异常UI组件
    @Override
    public void errorView(boolean state, String retryUrl) {
    }
    
}
```

（1）标题栏风格：
请标题栏风格 根据业务需求设置。

（2）标题栏 右侧 RightButton 参数解释：

| 名称 | 类型 | 必须? | 描述 |
| --- | --- | --- | --- |
| icon | String | 否 | 按钮图片 |
| text | String | 否 | 按钮标题 |
| loadSelf | Bool | 否 | `默认false`: 是否在当前页面打开 |
| targetUrl | String | 是 | `close`:  关闭当前页面</br> \<url>: 打开这个url |


