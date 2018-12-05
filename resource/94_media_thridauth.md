# 媒体模块

## 授权流程

### 说明

时序图：
![](media/15439311563408.jpg)

### 三方授权 SDK 文档

QQ SDK 文档： [点击查看](http://wiki.open.qq.com/wiki/%E9%A6%96%E9%A1%B5)

微信SDK 文档：[点击查看](https://open.weixin.qq.com/cgi-bin/showdocument?action=dir_list&t=resource/res_list&verify=1&id=open1419317851&token=d0068cccc332e748ea5a18522d8348e872953c88&lang=zh_CN)

喜马拉雅 文档：[点击查看](http://open.ximalaya.com/doc/sdk-access)

---

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
 
----

### 上报 QQ 授权信息

QQ 账号授权成功后，需要上报信息。

参数说明：

| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| uploadInfo |  UploadInfoBean | 是 | QQ SDK 返回的授权信息  |
| thirdOauthInfoBean |  ThirdOauthInfoBean | 是 | 上面 三方信息获取到的实体  |
| deviceTypeId |  String | 是 | 设备类型Id  |

Kotlin

```Kotlin
var uploadInfo = UploadInfoBean.newBuilder()
                    .openid(qqAuthResult.getOpenid()) // QQ SDK 返回的 Openid
                    .accessToken(qqAuthResult.getAccess_token()) // QQ SDK 返回的 Access_token
                    .expiresIn(qqAuthResult.getExpires_in()) // QQ SDK 返回的tExpires_in
                    .createTime( Date().getTime()) // 当前系统时间
                    .build()
            
RokidMobileSDK.media.thirdAuth().uploadQQBind(uploadInfo, thirdOauthInfoBean, deviceTypeId, object : IUploadThirdAuthCallback{
    override fun onSucceed() {
        //...
     }

    override fun onFailed(errorCode: String?, errorMsg: String?) {
        //...
    }

 })
```

---

### 上报 微信 授权信息

微信 账号授权成功后，需要上报信息。

参数说明：

| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| code |  UploadInfoBean | 是 | 微信 SDK 返回的授权信息  |
| thirdOauthInfoBean |  ThirdOauthInfoBean | 是 | 上面 三方信息获取到的实体  |
| deviceTypeId |  String | 是 | 设备类型Id  |

Kotlin

```Kotlin
RokidMobileSDK.media.thirdAuth().uploadWXBind(code, deviceTypeId, thirdOauthInfoBean, object : IUploadThirdAuthCallback {
    override fun onSucceed() {
        //...            
    }

    override fun onFailed(errorCode: String?, errorMsg: String?) {
        //..
    }
})
```

