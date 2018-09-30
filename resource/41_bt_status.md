# 绑定模块 Binder

#### 查询蓝牙状态
 
 **接口说明** 
 
 查询手机蓝牙状态，是否打开。

 **举个大栗子:**
 
 ```java
boolean btStatus = RokidMobileSDK.binder.getBTStatus()
 ```

---

#### 注册蓝牙状态监听器

 **接口说明**
 
 监听手机蓝牙状态发生改变，手机蓝牙打开 或者 关闭都会调用这个函数。

 **举个大栗子:**

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

