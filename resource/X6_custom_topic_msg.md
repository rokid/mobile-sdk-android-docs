# 自定义消息

## 简介

此消息 用来接收 用户自定义TOPIC消息 发送过来的事件。

## event名称

ChannelMessageBean

### 例子

Kotlin

```kotlin
@Subscribe(threadMode = ThreadMode.MAIN)
fun onReceiveCustomMessage(customEvent: ChannelMessageBean) {
    // TODO
}
```

ChannelMessageBean 说明：

| 参数 | 类型 | 说明 |
| --- | --- | --- |
| sourceDevice | ChannelDeviceBean| 发送消息对象 |
| reviceDevice | ChannelDeviceBean | 接收消息对象 |
| topic | String | 自定义消息名称 |
| text | String | 自定义消息内容|

ChannelDeviceBean 说明：

| 参数 | 类型 | 说明 |
| --- | --- | --- |
| accountId | String| 账号Id|
| deviceId|String | 设备Id | |
| deviceTypeId| String | 设备类型 |



