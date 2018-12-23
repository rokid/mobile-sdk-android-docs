# 媒体模块

## 授权交互流程

![](media/15439311563408.jpg)

### 获取已授权信息

参数说明：

| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| type | ThirdAuth | 是 | 获取第三方授权信息标识。<br>如：ThirdAuth.QQ、ThirdAuth.WX、ThirdAuth.XMLY  |
| deviceTypeId | String | 是 | 设备类型 | 
| deviceId  | String | 是 | 设备SN | 

ThirdOauthToken 说明

| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| access_token | String | 是 | 授权 Token | 
| expires_in | String | 是 | 有效期 | 
| refresh_token | String | 是 | 刷新所需 Token | 
| type | String | 是 | 获取第三方授权信息标识 | 

举个大栗子

Kotlin

```Kotlin
RokidMobileSDK.media.thirdAuth().getThirdOauthToken(ThirdAuth.QQ, device.device_type_id, device.deviceId, object : IGetThirdOauthTokenCallback {

    override fun onGetThirdOauthTokenSucceed(thirdOauthToken: ThirdOauthToken?) {
        Logger.d("onSucceed - ${thirdOauthToken.toString()}")
    }

    override fun onGetThirdOauthTokenFailed(errorCode: String?, errorMsg: String?) {
        Logger.e("onFailed - errorCode: ${errorCode}; errorMessage: ${errorMsg}")
    }

})
```

---

### 获取 三方平台授权所需信息

参数说明：

| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| type | ThirdAuth | 是 | 获取第三方授权信息标识。<br>如：ThirdAuth.QQ、ThirdAuth.XMLY  |
| deviceTypeId | String | 是 | 设备类型 | 

ThirdOauthInfoBean 说明

| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| baseAppId | String | 是 |  第三方平台申请的 AppId |
| baseAppSecret | String | 是 | 第三方平台申请的 AppSecret |
| baseRedirectUri | String | 是 | 授权完成，信息上报地址 |
| callbackThirdUrl | String | 是 | 授权完成，回调地址 |

举个大栗子

Kotlin

```Kotlin
RokidMobileSDK.media.thirdAuth().getThirdOauthInfo(ThirdAuth.QQ, "deviceTypeId", 
object : IGetThirdOauthInfoCallback {

    override fun onGetThirdOauthInfoSucceed(thirdOauthInfoBean: ThirdOauthInfoBean?) {
        // ...
    }

    override fun onGetThirdOauthInfoFailed(errorCode: String?, errorMsg: String?) {
        // ...
    }

 })
```

---

### 解除绑定

解绑 第三方授权。

参数说明：

| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| type | ThirdAuth | 是 | 获取第三方授权信息标识。<br>如：ThirdAuth.QQ、ThirdAuth.XMLY  |

举个大栗子

Kotlin

```Kotlin
RokidMobileSDK.media.thirdAuth().unbindThirdAuth(ThirdAuth.QQ, object : IUnbindAuthCallback {
    override fun onSucceed() {
        // ...
    }

    override fun onFailed(errorCode: String?, errorMsg: String?) {
        // ...
    }
 })
```

