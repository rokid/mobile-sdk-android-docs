# 设备音量

###  获取设备音量

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

---

### 更改设备音量

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

---

### 设备音量发生变化

当在设备上音量发送变化时，Mobile SDK 会收到 音量改变消息。

### 消息体

EventVolumeChange 

### 例子

Kotlin

```kotlin
@Subscribe(threadMode = ThreadMode.BACKGROUND)
public fun onReceived(eventVolumeChange: EventVolumeChange){
    // TODO
}
```

EventVolumeChange 说明：

| 参数 | 类型 | 说明 |
| --- | --- | --- |
| event | String | 固定值：ON_VOLUME_CHANGE |
| from | String | 设备Id |
| to | String | 用户Id |
||||
| volumeTemplate.mediaCurrent | String | 媒体当前音量 |
| volumeTemplate.mediaCurrentmediaTotal | String | 媒体最大音量 |
 
---


