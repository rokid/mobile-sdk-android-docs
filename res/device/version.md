# 设备系统

## 获取系统版本信息

**接口说明**

1. 获取当前设备的系统版本信息 返回的消息将以<font color=red size=3>Event</font>的形式向上抛。
2. 返回值 只表示 获取系统版本信息是否已经发送成功。

**参数说明**
 
| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| deviceId | String | 是 | 设备ID |

**示例代码**：
 
Kotlin
 
```kotlin
RokidMobileSDK.device.getVersionInfo(deviceId, object : IChannelPublishCallback {
override fun onSucceed() {
    // TODO
}

override fun onFailed() {
    // TODO
}
})
```
 
Event名称
 
EventDeviceSysUpdate
 
举个大栗子：
 
Kotlin

```kotlin
@Subscribe(threadMode = ThreadMode.BACKGROUND)
public fun onReceived(eventDeviceSysUpdate: EventDeviceSysUpdate){
// TODO
}
```
 
| 参数 | 类型 | 说明 |
| --- | --- | --- |
| from | String | 消息来源设备Id |
| to | String | 用户Id |
||||
| versionInfo.getCheckCode | int | 0:表示没有更新 ,1:表示有更新 |
| versionInfo.currentVersion | String | 当前版本 |
| versionInfo.changelog | String | 版本更新信息 |
 
**event数据格式** 
  
 ```json
{
    "from": "deviceId",
    "to": "userId",
    {
        //新版本的文案
        "changelog": "新版本文案",
        //0代表已经是最新版本 1，代表有新版本可以升级
        "checkCode": 0/1,
        //下载进度
        "downloadProgress": 96,
        //已经下载的大小
        "downloadedSize": 350407968,
        //已经
        "totalSize": 361678140,
        //true代表升级包下载完毕，可以升级，false代表正在下载
        "updateAvailable": true,
        "url": "http://cnpkg.rokidcdn.com/rokid-os/file/171121194749.zip",
        //版本号
        "version": "2.2.3-20171121.190617"
    }
}
 ```
 
## 开始系统升级

 **接口说明**
 
 1. 设备开始下载新的镜像 返回的消息和系统版本信息一致
 2. 返回值 只表示 获取系统版本信息是否已经发送成功。

 **参数说明**
 
| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| deviceId | String | 是 | 设备ID |

 **示例代码**：
 
 Kotlin
 
```kotlin
 RokidMobileSDK.device.startSystemUpdate(deviceId, object : IChannelPublishCallback {
    override fun onSucceed() {
        // TODO
    }

    override fun onFailed() {
        // TODO
    }
})
 ```
 
 **返回值说明**
 
| 字段    | 类型   | 说明 |
| ------ | -----  | ----- |
| sendSuccess | boolean | 发送是否成功 |

  <font color=red size=3>注：设备下载镜像成功后会重启，底层与设备的长连接会断，之后的这些接口将获取不到信息</font>
 
 ---

