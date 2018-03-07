# Vui 模块
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
boolean sendSuccess = RokidMobileSDK.home.sendTts(deviceId, tts);
```

Kotlin:

```kotlin
val sendSuccess = RokidMobileSDK.home.sendTts(deviceId, tts)
```
 
**返回参数说明**
 
| 字段    | 类型    | 说明 |
| ------ | ------- |  ----- |
|sendSuccess| boolean|是否发送成功|

---


