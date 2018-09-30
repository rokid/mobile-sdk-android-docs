# 设备模块 Device

## 设置设备的昵称前缀

 **接口说明**
 
 给新添加的设备设置一个默认的昵称前缀，如：Pebble
 
 **参数说明**
 
| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| nickPrefix | String | 是 | 昵称前缀 |


 **示例代码**：
 
 ```java
 RokidMobileSDK.device.setInitDeviceNickPrefix(nickPrefix);
 ```
 <font color='red'>
注：底层会截取该设备的deviceId后3位，再根据您设置的默认昵称前缀组成该设备的默认昵称，如：Pebble123。
</font>

 ---


