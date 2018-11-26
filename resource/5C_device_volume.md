# 设备模块 Device

##  获取设备音量

API 说明
    
先通过 SDK API 请求获取设备音量，再监听 SDKVolumeChange 来接收设备音量。

参数说明
 
| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| deviceId | String | 是 | 设备ID |

举个大栗子：

Kotlin

```Kotlin
val deviceId = "XXX"
RokidMobileSDK.device.getVolume(deviceId)

@Subscribe
fun onVolumeChange(sss: SDKVolumeChange) {
     // ...
}
```

## 设置设备音量

API 说明
    
先通过 SDK API 请求获取修改设备音量，再监听 SDKVolumeChange 来接收设备音量更改情况。

参数说明
 
| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| deviceId | String | 是 | 设备ID |
| volume | int | 是 | 音量数字 |

举个大栗子：

Kotlin

```Kotlin
val deviceId = "XXX"
RokidMobileSDK.device.changeVolume(deviceId, 100)

@Subscribe
fun onVolumeChange(sss: SDKVolumeChange) {
     // ...
}
```


