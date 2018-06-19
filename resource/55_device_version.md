# 设备模块 Device
## 1、获取系统版本信息

**接口说明**
1、获取当前设备的系统版本信息 返回的消息将以<font color=red size=3>Event</font>的形式向上抛。
2、返回值 只表示 获取系统版本信息是否已经发送成功。

 **参数说明**
 
| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| deviceId | String | 是 | 设备ID |

 **示例代码**：
 
 ```java
 boolean isSuccees = RokidMobileSDK.device.getVersionInfo(deviceId);
 ```
 
 **event名称**
 EventDeviceSysUpdate
 
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
 
## 2、开始系统升级

 **接口说明**
 1、设备开始下载新的镜像 返回的消息和系统版本信息一致
 2、返回值 只表示 获取系统版本信息是否已经发送成功。

 **参数说明**
 
| 字段    | 类型   | 必须？| 说明 |
| ------ | ----- | ----- | ----- |
| deviceId | String | 是 | 设备ID |

 **示例代码**：
 
 ```java
 boolean sendSuccess= RokidMobileSDK.device.startSystemUpdate(deviceId)
 ```
 
 **返回值说明**
 
| 字段    | 类型   | 说明 |
| ------ | -----  | ----- |
| sendSuccess | boolean | 发送是否成功 |

  <font color=red size=3>注：设备下载镜像成功后会重启，底层与设备的长连接会断，之后的这些接口将获取不到信息</font>
 
 ---

