# 设备模块 Device
## 更新设备的昵称

 **接口说明**
 更新当前设备的昵称
 
 **参数说明**
 
| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| deviceId | String | 是 | 设备ID |
| newNick | String | 是 | 新设备名称 | 

 **示例代码**：
 
 ```java
 RokidMobileSDK.device.updateNick(deviceId, newNick, new IUpdateNickNameCallback() {
    @Override
    public void onUpdateNickNameSucceed(String nickName) {
        Log.i("updateNick","onUpdateNickNameSucceed nickName="+nickName);
        ... // doSomeing
    }

    @Override
    public void onUpdateNickNameFailed(String errorCode, String errorMsg) {
        Log.e("updateNick","onUpdateNickNameFailed errorCode=" + errorCode + " errorMsg=" + errorMsg);
        ... // doSomeing
    }
 });
 ```
 
 ---

