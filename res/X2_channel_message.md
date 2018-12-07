# 通用消息

### 介绍

此消息体可以接收 Mobile SDK 发出的全部未经过 Mobile SDK 处理的原始消息。

### 消息体

SDKChannelMessage
 
### 例子

Kolin

```kotlin
@Subscribe(threadMode = ThreadMode.MAIN)
public fun onReceivedSDKChannelMessage(channelMessage: SDKChannelMessage){
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

