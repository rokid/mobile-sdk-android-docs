# 帐号模块 Account

## 1、登录接口
* 接口说明：需要传入token和用户id，ILoginResultCallback为获取登陆结果回调监听

**参数说明:**

| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| userId  | String | 是 | 用户id |

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

## 2、登出接口

* 接口说明：登出接口，清除 SDK 中的 token、userId 等缓存数据。

**示例代码：**

```java
RokidMobileSDK.account.logout(new ILogoutResultCallback() {
    @Override
    public void onLogoutSucceed() {
        Logger.d("onLogoutSucceed is called.");
        ... // do something
    }

     @Override
    public void onLogoutFailed(String errorCode, String errorMsg){
        Logger.e("onLogoutFailed errorCode=" + errorCode + " errorMsg=" + errorMsg);
        ... // do something
    }
});
```

## 3、用户登录 Token

* 接口说明：获取用户登录的 Token

**示例代码：**

```java
String token = RokidMobileSDK.account.getToken();
```

----

