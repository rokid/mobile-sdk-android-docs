# 媒体消息

## 简介

此消息 主要是 设备 响应语音指令后 发送过来的事件。

## event名称

SDKMediaEvent

### 例子

Kotlin

```kotlin
@Subscribe(threadMode = ThreadMode.MAIN)
fun onReceivedMediaMessage(sdkMediaEvent: SDKMediaEvent) {
    // TODO
}
```

SDKMediaEvent 说明：

| 参数 | 类型 | 说明 |
| --- | --- | --- |
| appId | String | 技能id |
| version | String | 内容协议版本号 |
| event | String | 事件名称 |
||||
| template.controlInfo.state | String | 内容播放状态: </br> PLAYING: 播放中;</br> PAUSED: 暂停播放;</br> STOPPED: 停止播放;</br> |


