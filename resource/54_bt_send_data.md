# 配网模块 Binder
## 设备配网

**接口说明** 
发送绑定数据（这里会发送到正在连接的蓝牙设备）

**参数说明**

| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| binderData | DeviceBinderData | 是 | 蓝牙发送信息 |

**示例代码**

```java
 // 构建绑定数据
 DeviceBinderData binderData = DeviceBinderData.newBuilder()
                .wifiPwd("your wifiPwd")        //wifi密码（可以为空）
                .wifiSsid("your wifiSsid")      //wifi名字（可以为空）
                .wifiBssid("your wifiBssid")    //wifi地址（可以为空）
                .build();
                
// 发送数据
RokidMobileSDK.binder.sendBTBinderData(binderData, new BTSendCallBack() {
    @Override
    public void sendSuccess(BTDeviceBean btDeviceBean) {    
        Log.i("BTSendCallBack","sendBtData Success name=" + btDeviceBean.getName());
        Log.i("BTSendCallBack","sendBtData Success address=" + btDeviceBean.getAddress());
        ... // doSomeing
     }

    @Override
    public void sendFailed(BTDeviceBean btDeviceBean, BleException bleException) {          
        Log.e("BTSendCallBack","sendBtData failed name=" + btDeviceBean.getName());
        Log.e("BTSendCallBack","sendBtData failed address=" + btDeviceBean.getAddress());
        Log.e("BTSendCallBack"," sendBtData failed Exception=" + bleException.toString());
        ... // doSomeing
    }
});
```

---


