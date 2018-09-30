# Mobile SDK 初始化

### 初始化

使用 Mobile SDK 之前必须要先初始化SDK，否则无法正常使用 Mobile SDK。

**注意:**

1. **<font color=red size=3>在工程的Application类的onCreate()方法中初始化RokidMobileSDK。</font>**
2. **<font color=red size=3>appKey、appSecret、accessKey 请按照真实填写，否则会初始化失败。</font>**
3. **<font color=red size=3>appKey、appSecret、accessKey 需要向 对接的 Rokid 项目经理 申请。</font>**

**参数说明：**

| 字段        | 类型    | 必须？| 说明 |
| ---------  | --------- | --- | --- |
| context | Context| 是 | Context |
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




