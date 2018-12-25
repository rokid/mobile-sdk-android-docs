# 设备模块 Device

## ping设备

接口说明
 
获取当前设备的在线状态
 
参数说明
 
| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
|sddDevice |SDKDevice | 是 | SDKDevice|


举个大栗子：
 
 ```java
  RokidMobileSDK.device.pingDevice(sddDevice, new IPingDeviceCallback() {

            @Override
            public void onSuccess(String deviceId, boolean isOnline) {
                showToast("获取设备状态成功,deviceId=" + deviceId + ",isOnline=" + isOnline);
            }

            @Override
            public void onFailed(String deviceId, String errorCode, String errorMsg) {
                showToast("获取设备状态失败，deviceId" + deviceId + ",errorCode=" + errorCode + "errorMsg= " + errorMsg);
            }
        });
 ```
 
 ---
 
## 设备状态发生变化

如果 设备在线状态 有变化时，Mobile SDK 会接收到以下消息。

### 消息体

EventDeviceStatus

举个大栗子：

Kotlin

```kotlin
@Subscribe(threadMode = ThreadMode.BACKGROUND)
public fun onReceived(eventDeviceStatus: EventDeviceStatus){
    // TODO
}
```

EventDeviceStatus 说明：

| 参数 | 类型 | 说明 |
| --- | --- | --- |
| deviceId | String | 当前设备Id |
| isOnline | boolean | 是否在线 |
 
---

## 当前设备状态发生变化

### 消息体

EventCurrentDeviceStatus 

举个大栗子：

Kotlin

```kotlin
@Subscribe(threadMode = ThreadMode.BACKGROUND)
public fun onReceived(eventCurrentDeviceStatus: EventCurrentDeviceStatus){
    // TODO
}
```
 
EventCurrentDeviceStatus 说明：

| 参数 | 类型 | 说明 |
| --- | --- | --- |
| deviceId | String | 当前设备Id |
| isOnline | boolean | 是否在线 |

---




