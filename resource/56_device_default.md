# 设备模块 Device
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
 
## 获取默认设备
**接口说明**
获取当前选择的设备。

**示例代码**：
 
```java
SDKDevice device = RokidMobileSDK.device.getCurrentDevice();
```
 
---


