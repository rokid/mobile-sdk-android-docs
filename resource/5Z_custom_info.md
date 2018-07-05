# 设备配置信息 Device

## 1、获取设备配置信息

根据业务需求获取设备 配置的各种信息。

参数说明

| 字段 | 类型 | 必须 | 备注 |
| --- | --- | --- | --- |
| deviceId | String | 是 | 设备Id |
| namespace | String | 是 | 存储空间、根据业务填写 |
| key | String | 是 | 信息存储Key |

**示例代码**：

Kotlin

```kotlin

val deviceId: String = "XXX"
val namespace: String = "YYY"
val key: String = "ZZZ"

RokidMobileSDK.device.getServiceInfo(deviceId, namespace, key,
    object : SDKServiceInfoCallback{
        override fun onSuccess(result: String?) {
            // TODO ...
        }
        
        override fun onFailed(errorCode: String?, errorMsg: String?) {
            // TODO ...
        }
})
```

## 2、存储、更新设备信息

| 字段 | 类型 | 必须 | 备注 |
| --- | --- | --- | --- |
| deviceId | String | 是 | 设备Id |
| namespace | String | 是 | 存储空间、根据业务填写 |
| kvMapJsonString | String | 是 | 信息存储信息键值对 转换成的 JsonString  |

```kotlin
val deviceId: String = "XXX"
val namespace: String = "YYY"
val kvMapJsonString: String = "ZZZ"

RokidMobileSDK.device.storeServiceInfo(deviceId, namespace, kvMapJsonString, object : SDKServiceInfoCallback {
    override fun onSuccess(result: String?) {
    }

    override fun onFailed(errorCode: String?, errorMsg: String?) {
    }

})
```

