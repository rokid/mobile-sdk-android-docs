# 发送配网数据

## 设备配网

**接口说明** 

发送绑定数据

这里会发送到正在连接的蓝牙设备

**参数说明**

| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| binderData | DeviceBinderData | 是 | 蓝牙发送信息 |

**举个大栗子**

```java
 // 构建绑定数据
 DeviceBinderData binderData = DeviceBinderData.newBuilder()
                .wifiPwd("your wifiPwd")        //wifi密码（可以为空）
                .wifiSsid("your wifiSsid")      //wifi名字（可以为空）
                .wifiBssid("your wifiBssid")    //wifi地址（可以为空）
                .build();
                
// 发送数据
RokidMobileSDK.binder.sendBTBinderData(binderData, new IBinderCallBack() {
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

## 配网状态

设备配网过程中，状态判断。
需要 使用 EventBus 接收 消息。

### 消息体

SDKBinderStatusEvent

### 状态值判断

| 状态值 | 说明 | 备注 |
| --- | --- | --- |
| 10 | wifi连接中 ||
| 11 | wifi连接成功 ||
| -11 | wifi密码错误 ||
| -12 | wifi连接超时 ||
| -13 | 没找到当前wifi ||
| -14 | wifi密码长度不正确 ||
| 100 | 登录中 ||
| 101 | 登录成功 ||
| -101 | 登录失败 ||
| 200 | 绑定中 ||
| 201 | 绑定成功 ||
| -201 | 绑定失败 ||

