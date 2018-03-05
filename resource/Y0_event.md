# SDK 发出的 Event 

<font color=red size=3>**目前Event 使用 EventBus 进行封装，请引入EventBus 库**</font>

**1、当期用户登录失效 或 异地登录**

**event名称**
EventUserLoginInvalid
 
---

**2、当前选择的设备发生变化**

**event名称**
EventCurrentDeviceChange

**消息格式**
 
 ```json
{
    "deviceId": "XXXXX"
}
 ```
 
---

**3、当前设备状态发生变化**

**event名称**
EventCurrentDeviceStatus 

**消息格式**
 
 ```json
{
    "deviceId": "XXXXX",
    "isOnline": true/false
}
 ```

---

**4、设备状态发生变化**

**event名称**
EventDeviceStatus

**消息格式**
 
 ```json
{
    "deviceId": "XXXXX",
    "isOnline": true/false
}
 ```
 
---

**5、设备解绑**

**event名称**
EventUnbinder

**消息格式**
 
 ```json
{
    "deviceId": "XXXXX"
}
 ```
 
---

**6、音量发生变化**

**event名称**
EventVolumeChange 

**消息格式**
 
 ```json
{
    "event": "ON_VOLUME_CHANGE",
    // 设备id
    "from": "deviceid",
    // 用户id
    "to": "userId",
    "volumeTemplate": {
        // 媒体当前音量
        "mediaCurrent": "8",
        // 媒体最大音量
        "mediaTotal": "15"
    }
}
 ```
 
 **7、系统更新信息**

**event名称**
EventDeviceSysUpdate 

**消息格式**
 
 ```json
{
    // 设备id
    "from": "deviceid",
    // 用户id
    "to": "userId",
    "VersionInfo": {
        "getCheckCode": 0, // 0:表示没有更新 ,1:表示有更新
        "currentVersion": "", // 当前版本
        "changelog": "" // 版本信息
    }
}
 ```
 


