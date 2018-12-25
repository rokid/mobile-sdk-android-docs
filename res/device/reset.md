# 恢复设备的出厂设置

#### 说明

此接口适用于恢复设备的出厂设置，设备回复出厂设置成功时，会发送一个 EventUnbind 给 Mobile SDK，我们需要接收消息 并在本地设备列表中 删除此设备。

举个大栗子：
 
Kotlin
 
```kotlin
RokidMobileSDK.device.resetDevice(deviceId, object : IChannelPublishCallback {
    override fun onSucceed() {
        // TODO
    }

    override fun onFailed() {
        // TODO
    }

})
```

---

#### 消息体

EventUnbind

举个大栗子：

Kotlin

```kotlin
@Subscribe(threadMode = ThreadMode.BACKGROUND)
public fun onReceived(eventUnbind: EventUnbind){
    // TODO
}
```

EventUnbind 说明：

| 参数 | 类型 | 说明 |
| --- | --- | --- |
| deviceId | String | 当前设备Id |

---

