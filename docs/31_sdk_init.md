# SDK 初始化
## 1、RokidMobileSDK 初始化

* 接口说明：RokidMobileSDK初始化。
* <font color=red size=3>**在工程的Application类的onCreate()方法中初始化RokidMobileSDK.**</font>
* appKey 和 appSecret 需要在若琪开放平台注册获取

**参数说明：**

| 字段         | 类型    | 必须？| 说明 |
| :---------  | --------- | :---: | --- |
| ApplicationContext | Context| 是 | Context |
| appKey | String | 是 | Rokid 发放的 appKey |
| appSecret | String | 是 | Rokid 发放的 appSecret |
| accessKey | String | 是 | Rokid 发放的 accessSecret |

**示例代码：**

```Java
RokidMobileSDK.init(context, appKey, appSecret, accessKey, new InitCompletedCallback) {
    @Override
    public void onInitSuccess() {
        Logger.d("onInitSuccess is called.");
        ... // do something
    }

    @Override
    public void onInitFailed(String errorCode, String errorMsg) {
        Logger.e("onInitFailed errorCode=" + errorCode + " errorMsg=" + errorMsg);
        ... // do something
    }
});
```

---

## 2、测试环境
调用此api 可以切换到 测试环境。

**示例代码：**

```Java
RokidMobileSDK.debug();
``` 


