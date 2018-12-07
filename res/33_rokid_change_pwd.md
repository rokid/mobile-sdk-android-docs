# 若琪账号体系

## 修改密码

接口

参数说明

| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| oldPasswd  | String | 是 | 旧密码 |
| newPassword   | String | 是  | 新密码 |

**举个大栗子：**

Kotlin

```kotlin
RokidMobileSDK.account.changePasswd("oldPasswd", "newPassword",
    object : IChangePasswordResultCallback {
        override fun onChangePasswordSucceed() {
                // ....
         }
         
         override fun onChangePasswordFailed(errorCode: String?, errorMessage: String?) {
                // ...
         }
})
```

Java:

```Java
RokidMobileSDK.account.changePasswd("oldPasswd", "newPassword",
    new  IChangePasswordResultCallback() {
    @Override
    public void onChangePasswordSucceed() {
        // ....
    }
         
    @Override
    public void onChangePasswordFailed(String: errorCode,  String: errorMessage) {
        // ...
    }
});
```


