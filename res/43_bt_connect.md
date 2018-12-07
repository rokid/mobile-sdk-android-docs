# 蓝牙连接

## 连接蓝牙设备

**接口说明**
接口需传入蓝牙名称（蓝牙address重启后会变）

**参数说明**

| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| name | String | 是 | 设备名称 |

**举个大栗子**

``` java
RokidMobileSDK.binder.connectBT(name, new IBTConnectCallBack() {
    @Override
    public void onConnectSucceed(BTDeviceBean btDeviceBean) {
        Log.i("BTConnectCallBack","connectBT Success name=" + btDeviceBean.getName());
        Log.i("BTConnectCallBack","connectBT Success address=" + btDeviceBean.getAddress());
        ... // doSomeing
    }

    @Override
    public void onConnectFailed(BTDeviceBean btDeviceBean, BleException bleException) {
        Log.e("BTConnectCallBack","connectBT Failed name=" + btDeviceBean.getName());
        Log.e("BTConnectCallBack","connectBT Failed address=" + btDeviceBean.getAddress());
        Log.e("BTConnectCallBack","connectBT Failed Exception=" + bleException.toString() );
        ... // doSomeing
    }
});
```
                               
---


