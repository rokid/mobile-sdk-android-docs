# 设备模块 Device

## 获取默认设备

**接口说明**

获取当前选择的设备。

**示例代码**：
 
```java
SDKDevice device = RokidMobileSDK.device.getCurrentDevice();
```
 
---

## 设置默认设备

**接口说明**

更新当前选择设备
 
**参数说明**
 
| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| device | SDKDevice | 是 | 若琪设备实体 |

**示例代码**：
 
```java
RokidMobileSDK.device.setCurrentDevice(device);
```
 
---

## 当前选择的设备发生变化

### 消息体

EventCurrentDeviceChange

### 例子

Kotlin

```kotlin
@Subscribe(threadMode = ThreadMode.BACKGROUND)
public fun onReceived(eventCurrentDeviceChange: EventCurrentDeviceChange){
    // TODO
}
```

EventCurrentDeviceChange 说明：

| 参数 | 类型 | 说明 |
| --- | --- | --- |
| deviceId | String | 当前设备Id |
 
---


