# 设备模块 Device

## 获取设备列表

**接口说明**

```
目前获取服务端 masterId 对应的设备列表，
底层会默认给用户选择一个当前设备，逻辑图如下：
```
 
 ![](media/currentDevice.png)
 
 **示例代码**
 
 ```java
 RokidMobileSDK.device.getDeviceList(new SDKGetDeviceListCallback() {
        @Override
        public void onGetDeviceListSucceed(List<SDKDevice> deviceList) {
            if(CollectionUtils.isEmpty(devices)) {
                ... // doSomeing 
                return;
            }
                
        Logger.i("onGetDeviceListSucceed device size="+devices.size());
            ... // doSomeing 
        }

        @Override
        public void onGetDeviceListFailed(String errorCode, String errorMsg) {
            Logger.e("onGetDeviceListFailed errorCode"+errorCode+", errorMsg="+errorMsg );
               ... // doSomeing
        }
 });
 ```
 
  **deviceList数据格式**：
   
 ```json
[
    {
        // 设备昵称
        "deviceNick": "xxx",   
        // 设备Id          
        "deviceId": "0011111111111111",   
         // 设备地区             
        "region": "CN",
        "sn": "02010217020001ED",
        // 系统版本号
        "ota": "2.2.2-20171027.091126",
        // mac地址
        "mac": "02:00:00:00:00:00",
        "ip": "183.129.185.66",
        // 局域网 IP
        "lan_ip":"192.168.1.156",
        // 自定义TTS音色
        "ttsList": "[{\"name\":\"111777\",\"vibrato\":0,\"speed\":0,\"formant\":0,\"tone\":0},{\"name\":\"234566777777\",\"vibrato\":4,\"speed\":5,\"formant\":-5,\"tone\":5},{\"name\":\"5555\",\"vibrato\":-5,\"speed\":5,\"formant\":-5,\"tone\":-5}]",
        // 系统当前选择TTS音色
        "tts": "{\"formant\":-3,\"speed\":-2,\"tone\":1,\"ttsName\":\"蜡笔小新\"}",
        // 设备类型ID
        "device_type_id":"XXXX"
    }
]
 ```
 

