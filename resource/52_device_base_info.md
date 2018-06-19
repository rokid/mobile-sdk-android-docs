# 设备模块 Device
## 获取设备基本信息
 
 **接口说明**
获取 设备基本信息包括：ip、局域网ip、mac、nick、cy、sn、version、device_type_id
 
 **参数说明**
 
| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| deviceId | String | 是 | 设备ID |

**示例代码**：
 
 ```java
BasicInfo basicInfo = RokidMobileSDK.device.getBasicInfo(deviceId);
 ```
 
 ---  
 

