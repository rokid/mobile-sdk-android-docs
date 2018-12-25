# 设备抢绑

### 说明

当设备被其他账号绑走时，Mobile SDK 会收到以下消息。

#### 消息体

SDKChannelMessage
 
##### Topic

UNIVERSAL_UNBIND_TO_USER

##### 例子

Kolin

```kotlin
@Subscribe(threadMode = ThreadMode.MAIN)
fun onReceivedDeviceUnbind(channelMessage: SDKChannelMessage) {
    if (!"UNIVERSAL_UNBIND_TO_USER".equals(channelMessage.topic)) {
        return
    }

    // TODO
}
``` 

ChannelMessageBean 说明：

| 参数 | 类型 | 说明 |
| --- | --- | --- |
| sourceDevice | ChannelDeviceBean| 发送消息对象 |
| reviceDevice | ChannelDeviceBean | 接收消息对象 |
| topic | String | 消息类型 |
| text | String | 消息结构体 |

ChannelDeviceBean 说明：

| 参数 | 类型 | 说明 |
| --- | --- | --- |
| accountId | String| 账号Id|
| deviceId|String | 设备Id |
| deviceTypeId| String | 设备类型 |

