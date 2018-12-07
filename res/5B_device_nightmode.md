# 设备模块 Device

## 获取设备夜间模式

 **接口说明**
 
 获取设备夜间模式
 
 **参数说明**
 
| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| deviceId | String | 是 | 设备ID |

 **示例代码**：
 
 ```java
 String deviceId = "XXXXXX";
 RokidMobileSDK.device.getNightMode(deviceId, new IGetDeviceNightMode() {
            @Override
            public void onGetDeviceNightModeSucceed(NightModeBean nightModeBean) {
                // 获取成功
            }

            @Override
            public void onGetDeviceNightModeFailed(String errorCode, String errorMsg) {
                // 获取失败
            }
        });
)
 ```

---
 
## 更新设备夜间模式

 **接口说明**
 
 更新设备夜间模式
 
 **参数说明**

| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| deviceId | String | 是 | 设备ID |

NightModeBean 对象结构如下:

| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| action | String | 是 | open: 打开夜间模式</br>close: |
| startTime | String | 是 | 设备ID |
| endTime | String | 是 | 设备ID |

 **示例代码**：
 
 ```java
 String deviceId = "XXXXXX";
 
 NightModeBean nightModeBean = new NightModeBean();
 nightModeBean.setAction("open")
 nightModeBean.setStartTime("23:00")
 nightModeBean.setEndTime("7:00")
 
 RokidMobileSDK.device.updateNightMode(deviceId, nightModeBean, new IUpdateCustomInfoCallback() {
            @Override
            public void onUpdateDeviceNightModeSucceed() {
                callback.onUpdateDeviceNightModeSucceed();
            }

            @Override
            public void onUpdateDeviceNightModeFailed(String errorCode, String errorMsg) {
                callback.onUpdateDeviceNightModeFailed(errorCode, errorMsg);
            }
        });
)
 ```


