# 设备蓝牙扫描

#### 扫描设备

**介绍**

需要传入扫描蓝牙设备的名称的前缀，回调均在主线程。

<font color=red size=3>如果传空，是无法获取设备列表。</font>

---

1、单前缀蓝牙设备

**参数说明**

| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| type | String | 是 | 设备名称类型前缀 |

**举个大栗子**

``` java
String type = "Rokid-"
RokidMobileSDK.binder.startBTScan(type, new IBTScanCallBack() {
    @Override
    public void onNewDevicesFound(BTDeviceBean btDeviceBean) {
        if(null == btDeviceBean){
            Logger.w("BTScanCallBack", "newDevicesFound btDeviceBean is null");
            return;
        }
        
        Logger.i("BTScanCallBack","newDevicesFound device Name=" + btDeviceBean.getName())
        Logger.i("BTScanCallBack","newDevicesFound device Address=" + btDeviceBean.getAddress())
        
        ... // doSomeThing
});
```

---

2、多前缀蓝牙设备

**参数说明**

| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| types | String[] | 是 | 设备名称类型前缀列表 |

**举个大栗子**

``` java
String[] types = {"Rokid-Pebble-","Rokid-Mini-"}
RokidMobileSDK.binder.startBTScan(types, new IBTScanCallBack() {
    @Override
    public void onNewDevicesFound(BTDeviceBean btDeviceBean) {
        if(null == btDeviceBean){
            Logger.w("BTScanCallBack", "newDevicesFound btDeviceBean is null");
            return;
        }
        
        Logger.i("BTScanCallBack","newDevicesFound device Name=" + btDeviceBean.getName())
        Logger.i("BTScanCallBack","newDevicesFound device Address=" + btDeviceBean.getAddress())
        
        ... // doSomeThing
});
```

---

#### 停止蓝牙扫描 

**接口说明**

仅停止蓝牙扫描

**举个大栗子**

```java
 RokidMobileSDK.binder.stopBTScan()
```

---

#### 停止扫描并清除设备列表

**接口说明**

 停止扫描并且清除底层内存上的设备列表，建议在刷新的时候调用

**举个大栗子**

```java
 RokidMobileSDK.binder.stopBTScanAndClearList()
```

---

