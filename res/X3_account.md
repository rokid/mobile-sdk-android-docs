# 帐号 消息

## 帐号被登出

当前用户登录失效、异地登录时，都会发送这个消息。

### 消息体

EventUserLoginInvalid
 
### 例子

Kolin

```kotlin
@Subscribe(threadMode = ThreadMode.MAIN)
public fun onReceivedUserEvent(eventUserLoginInvalid: EventUserLoginInvalid){
    // TODO        
}
``` 

