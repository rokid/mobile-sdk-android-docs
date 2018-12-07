# 设备模块 Device

## ping设备

 **接口说明**
 
 获取当前设备的在线状态
 
 **参数说明**
 
| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
|sddDevice |SDKDevice | 是 | SDKDevice|


 **示例代码**：
 
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


