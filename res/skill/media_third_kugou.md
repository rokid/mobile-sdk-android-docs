# 酷狗音乐 Skill 授权

### 概述

本文档适用于第三方厂商使用酷狗音乐技能。用户登录酷狗音乐账号并获取token，使用酷狗音乐账号token将酷狗音乐账号与Rokid账号进行绑定。

### 说明

时序图：

![酷狗音乐](media/media_third_kugou.png)

### 上报`酷狗音乐`授权信息

上传酷狗登录成功后的用户相关信息

入参：

| 字段          | 类型         | 是否必须  | 说明                 |
| ------------ | ------------ | -------- | ------------------- |
| deviceId     | String       | 是       | 设备Id号             |
| deviceTypeId | String       | 是       | 设备类型Id           |
| tokenInfo    | String       | 是       | 酷狗登录成功的用户信息 |
| callback     | VoidCallback | 否       | 请求回调             |


【备注】

酷狗登录接口返回

```
{"status":1,
"error_code":0,
"data":{"nickname":"1409720***","token":"f0a5650469c31c3cc8abd1***","sex":2,"username":"1345***","pic":"http:\/\/imge.kugou.com\/kugouicon\/165\/20100101\/20100101192931478054.jpg","userid":"1409***"}
}
```

`tokenInfo`取酷狗音乐登录响应的"data"字段对应的Json字符串



Kotlin

```Kotlin
RokidMobileSDK.media.thirdAuth().uploadKuGouBind(deviceTypeId, deviceId, tokenJson, object : VoidCallback() {
    override fun onSucceed() {
        //...
    }

    override fun onFailed(code: String, message: String) {
        //...
    }
})
```
