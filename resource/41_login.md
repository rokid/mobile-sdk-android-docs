# 帐号 Account 模块
## Token登录接口
* 接口说明：SDK接入方用户Id，ILoginResultCallback为获取登陆结果回调监听

**参数说明:**

| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| userId  | String | 是 | SDK接入方用户Id |

**示例代码：**

```java
RokidMobileSDK.account.tokenLogin(userId, new ILoginResultCallback() {
    @Override
    public void onLoginSucceed() {
        Logger.d("onLoginSuccess is called.");
        ... // do something
    }

    @Override
    public void onLoginFailed(String errorCode, String errorMsg) {
        Logger.e("onLoginFailed errorCode=" + errorCode + " errorMsg=" + errorMsg);
        ... // do something
    }
});
```


