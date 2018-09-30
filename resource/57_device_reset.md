# 设备模块 Device

## 恢复设备的出厂设置

**接口说明**

恢复设备的出厂设置

**示例代码**：
 
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

