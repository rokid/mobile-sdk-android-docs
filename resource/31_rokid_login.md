# 若琪账号体系

## 注册流程

**1、流程**

![](images/rokid_register.png)

**2、接口**

1、获取 验证码

参数说明:

| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| phoneNum  | String | 是 | 手机号 |

举个大栗子:
    
```java
RokidMobileSDK.account.getScode(phoneNum, new IGetScodeResultCallback() {
    @Override
    public void onGetScodeSucceed() {
        Logger.d("onGetScodeSucceed is called.");
        ... // do something
    }

    @Override
    public void onGetScodeFailed(String errorCode, String errorMsg) {
        Logger.e("onGetScodeFailed errorCode=" + errorCode + " errorMsg=" + errorMsg);
        ... // do something
    }
});
```


2、验证 验证码

参数说明:

| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| phoneNum  | String | 是 | 手机号 |
| scode   | String | 否 | 验证码 |

举个大栗子:

```java
RokidMobileSDK.account.checkScode(scode, phoneNum, new ICheckScodeResultCallback() {
    @Override
    public void onCheckScodeSucceed(String newCode) {
        Logger.d("onCheckScodeSucceed is called.");
        ... // do something
    }

    @Override
    public void onCheckScodeFailed(String errorCode, String errorMsg) {
        Logger.e("onCheckScodeFailed errorCode=" + errorCode + " errorMsg=" + errorMsg);
            ... // do something
    }
});
```

3、注册账号

参数说明:

| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| phoneNum  | String | 是 | 手机号 |
| passwd   | String | 否 | 密码 |
| scode   | String | 否 | 验证码 |

举个大栗子:

```java
RokidMobileSDK.account.register(phoneNum, passwd, scode, new IRegisterResultCallback() {
    @Override
    public void onRegisterSucceed() {
        Logger.d("onRegisterSucceed is called.");
        ... // do something
    }

    @Override
    public void onRegisterFailed(String errorCode, String errorMsg) {
        Logger.e("onRegisterFailed errorCode=" + errorCode + " errorMsg=" + errorMsg);
        ... // do something
    }
});
```

## 登录流程

1、流程

![](images/rokid_login.png)

2、接口

参数说明

| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| phoneNum  | String | 是 | 手机号 |
| passwd   | String | 否 | 密码 |

**举个大栗子：**

Java:

```java
RokidMobileSDK.account.login(phoneNum, passwd, new ILoginResultCallback() {
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

