# Vui 模块
## 发送Topic消息
发送Topic消息，可以指定消息类型，

**参数说明**
 
| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| deviceId | String | 是 | 设备Id  |
| topic | String | 是 | 消息主题  |
| text | String | 是 | 消息文本  |

**示例代码**：
 
Java:
 
```java
RokidMobileSDK.vui.sendMessage(deviceId,topic, text, new IChannelPublishCallback() {
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
RokidMobileSDK.vui..sendMessage(deviceId,topic, text, object : IChannelPublishCallback {
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



