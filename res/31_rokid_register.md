# 若琪账号体系

## 注册流程

### 1、流程

![](media/rokid_register.png)

### 2、接口

#### 1、获取验证码（旧接口，推荐使用下面[新接口](#2、获取验证码)）

国际区号默认采用中国国际区号：”+86“

参数说明:

| 字段        | 类型   | 必须？| 说明                 |
| ---------- | ----- | ----- | ------------------- |
| phoneNum   | String | 是 | 手机号                  |

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

#### 2、获取验证码

参数说明:

| 字段        | 类型   | 必须？| 说明                 |
| ---------- | ----- | ----- | ------------------- |
| phoneNum   | String | 是 | 手机号                  |
| regionCode | String | 是 | 国际区号，例如中国为“+86“ |

举个大栗子:
    
```java
RokidMobileSDK.account.getScodeWithRegionCode(phoneNum, regionCode, new IGetScodeResultCallback() {
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


#### 3、校验验证码

参数说明:

| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| phoneNum  | String | 是 | 手机号 |
| scode   | String | 是 | 验证码 |

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

#### 4、注册账号

参数说明:

| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| phoneNum  | String | 是 | 手机号 |
| passwd   | String | 是 | 密码 |
| scode   | String | 是 | 手机发送的短信验证码 |
| areaCode  | String | 是 | 手机号码所属区域号，比如：“+86” |

举个大栗子:

```java
RokidMobileSDK.account.register(phoneNum, 
                passwd, 
                scode, 
                areaCode, 
                new IRegisterResultCallback() {
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


