# Vui 模块

## 流程

![](media/vui_tts.png)

## 发送TTS 

发送 TTS，就是 发送一条 能让设备立即说的 内容。

**参数说明**
 
| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| deviceId | String | 是 | 设备Id  |
| tts | String | 是 | 让设备说的话  |

**示例代码**：
 
 Java:
 
```java
RokidMobileSDK.vui.sendTts(deviceId, tts, new IChannelPublishCallback() {
    @Override
    public void onSucceed() {
        // TODO
    }

    @Override
    public void onFailed() {
        // TODO
    }

});
```

Kotlin:

```kotlin
RokidMobileSDK.vui.sendTts(deviceId, tts, object : IChannelPublishCallback {
    override fun onSucceed() {
        // TODO
    }

    override fun onFailed() {
     // TODO
    }

})
```
 
**返回参数说明**
 
| 字段    | 类型    | 说明 |
| ------ | ------- |  ----- |
|sendSuccess| boolean|是否发送成功|

---


