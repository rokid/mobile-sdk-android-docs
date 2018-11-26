# 自有帐号体系

注意：

使用 自有账号体系时，开发者必须拥有自己的账号体系，如果没有请直接使用 若琪账号体系，谢谢。

## 登录流程

1、流程

![](images/rokid_login.png)

2、接口

**参数说明:**

| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| userId  | String | 是 | SDK接入方用户Id |
| token   | String | 否 | SDK接入方用户token |

**举个大栗子:**

Java:

```java
RokidMobileSDK.account.thirdpartyLogin(userId, token, new ILoginResultCallback() {
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


