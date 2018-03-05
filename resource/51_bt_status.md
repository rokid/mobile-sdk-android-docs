# 配网模块 Binder
## 1、获取蓝牙状态
 
 **接口说明** 
 获取蓝牙当前状态

 **示例代码**
 
 ```java
boolean btStatus = RokidMobileSDK.binder.getBTStatus()
 ```

---

## 2、注册蓝牙状态监听器

 **接口说明**
 蓝牙状态发生改变的状态监听

 **示例代码**

```java
RokidMobileSDK.binder.registerBTStateChangeListener(new IBTStateChangeListener() {
    @Override
    public void onBluetoothStateChanged(boolean isOpen) {
        Logger.d("onBluetoothStateChanged ble state=" + isOpen);
        
        if (!isOpen) {
            // 蓝牙状态变成关
            ... // doSomeThing
            return;
        }
                 
        // 蓝牙状态变成开 
        ... //doSomeThing
    }
});    

```

---

