# 配网模块 Binder
## 1、扫描蓝牙设备

**接口说明**
需要传入扫描蓝牙设备的名称的前缀，如果传空，你将在回调里拿不到设备，请务必传入自己需要扫描蓝牙设备的前缀，回调均在主线程

**参数说明**

| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| type | String | 是 | 设备名称类型前缀 |

**示例代码**

``` java
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

## 2、停止蓝牙扫描 

**接口说明**
仅停止蓝牙扫描

**示例代码**

```java
 RokidMobileSDK.binder.stopBTScan()
```

---

## 3、停止扫描并清除设备列表

**接口说明**
 停止扫描并且清除底层内存上的设备列表，建议在刷新的时候调用

**示例代码**

```java
 RokidMobileSDK.binder.stopBTScanAndClearList()
```

---

