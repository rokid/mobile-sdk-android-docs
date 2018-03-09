# Vui 模块
## 发送ASR 
发送 ASR，就是发送 指定，让设备根据指令进行操作。

**参数说明**
 
| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| deviceId | String | 是 | 设备Id  |
| asr | String | 是 | 你对设备说的话  |

**示例代码**：
 
Java:
 
```java
boolean sendSuccess = RokidMobileSDK.vui.sendAsr(deviceId, asr);
```
 
Kotlin:
 
```kotlin
val sendSuccess = RokidMobileSDK.vui.sendAsr(deviceId, asr)
```
 
**返回参数说明**
 
| 字段    | 类型    | 说明 |
| ------ | ------- |  ----- |
|sendSuccess| boolean|是否发送成功|

---


