# 帐号信息 Account Info

## 获取用户信息

**接口定义**

Kotlin

```kotlin
RokidMobileSDK.account.fetchUserInfo(object : SDKFetchUserInfoCallback {
    override fun onSucceed(data: SDKUserInfo?) {
        
    }

    override fun onFailed(errorCode: String?, errorMsg: String?) {
        
    }
})
```

Java

```java
RokidMobileSDK.account.fetchUserInfo(new SDKFetchUserInfoCallback(){
    @Override
    public void onSucceed(SDKUserInfo sdkUserInfo) {
                
    }

    @Override
    public void onFailed(String errorCode, String errorMsg) {

    }
});
```

## SDKUserInfo
| 字段    | 类型   | 说明 |
| ------ | ----- | ----- |
| birthday | String | 生日 “2019/07/08” |
| userId | String | 用户 id |
| nickname | String | 用户昵称 |
| gender | String | 用户性别 如：“male” ”female“ |

# 更新用户信息

**接口定义**

Kotlin

```kotlin
RokidMobileSDK.account.updateUserInfo(nickname, gender, birthday, object : VoidCallback {
        override fun onSucceed() {

        }

        override fun onFailed(code: String, message: String) {
        
        }
}) 
```

Java

```java
RokidMobileSDK.account.updateUserInfo(nickname, gender, birthday, new VoidCallback() {
    @Override
    public void onSucceed() {
                
    }

    @Override
    public void onFailed(String errorCode, String errorMsg) {

    }
});
```

**参数说明**

| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| nickname | String | 是 | 用户昵称 |
| gender | String | 是 | 用户性别 如：“male” ”female“ |
| birthday | String | 是 | 生日 如：“2019/07/08” |

## Token

接口说明：获取用户登录的 Token

**举个大栗子:**

```java
String token = RokidMobileSDK.account.getToken();
```

----

## UserId

接口说明：获取用户登录的 UserId

**举个大栗子:**

```java
String userId = RokidMobileSDK.account.getUserId();
```

----



