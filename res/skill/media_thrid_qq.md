# 媒体模块

### 概述

本文档适用用第三方厂商，使用 Rokid QQ音乐、QQ叮当音乐 技能时，需要 QQ音乐token。作用于授权成功后，QQ音乐token 和 rokid账户进行绑定

### 准备阶段

在 QQ开发平台、微信开放平台 平台申请 key，secret
将申请的 key、secret 提供给 Rokid 。

### 说明

时序图：
![](media/15439311563408.jpg)

### 三方授权 SDK 文档

QQ SDK 文档： [点击查看](http://wiki.open.qq.com/wiki/%E9%A6%96%E9%A1%B5)

微信SDK 文档：[点击查看](https://open.weixin.qq.com/cgi-bin/showdocument?action=dir_list&t=resource/res_list&verify=1&id=open1419317851&token=d0068cccc332e748ea5a18522d8348e872953c88&lang=zh_CN)

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

