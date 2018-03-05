# 设备模块 Device
## 解绑设备

**接口说明** 
 解绑设备

**参数说明**
 
| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| deviceId | String | 是 | 设备ID |

**示例代码**：
 
```java
RokidMobileSDK.device.unbindDevice(deviceId, new IUnbindDeviceCallback() {
        @Override
        public void onUnbindDeviceSucceed() {
            Log.i("unbinderDevice","onUnbinderDeviceSuccess rokidId=" + rokiId);
            ... // doSomeing    
        }

        @Override
        public void onUnbindDeviceFailed(String errorCode, String errorMsg) {
            Log.i("unbinderDevice","onUnbinderDeviceFailed errorCode=" + errorCode + " errorMsg=" + errorMsg + " rokidId=" + rokiId);
            ... // doSomeing  
        }
 });
```
 
---


